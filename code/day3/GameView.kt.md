```kotlin
import android.content.Context
import android.graphics.Canvas
import android.graphics.Color
import android.graphics.Paint
import android.view.SurfaceHolder
import android.view.SurfaceView
import kotlin.math.abs

class GameView(context: Context) : SurfaceView(context), SurfaceHolder.Callback {
    private val paint = Paint()
    private var ballX = 300f
    private var ballY = 300f
    private var velocityX = 10f
    private var velocityY = 10f
    private val ballRadius = 50f
    private var isRunning = true

    init {
        holder.addCallback(this)
        startGameLoop()
    }

    private fun startGameLoop() {
        Thread {
            while (isRunning) {
                updatePhysics()
                drawCanvas()
                Thread.sleep(16) // ~60 FPS
            }
        }.start()
    }

    private fun updatePhysics() {
        ballX += velocityX
        ballY += velocityY

        // Handle boundary collisions
        if (ballX - ballRadius < 0 || ballX + ballRadius > width) {
            velocityX = -velocityX
        }
        if (ballY - ballRadius < 0 || ballY + ballRadius > height) {
            velocityY = -velocityY
        }
    }

    private fun drawCanvas() {
        val canvas = holder.lockCanvas()
        canvas.drawColor(Color.BLACK) // Clear screen

        paint.color = Color.RED
        canvas.drawCircle(ballX, ballY, ballRadius, paint)

        holder.unlockCanvasAndPost(canvas)
    }

    override fun surfaceCreated(holder: SurfaceHolder) {
        // No additional setup required for this example
    }

    override fun surfaceChanged(holder: SurfaceHolder, format: Int, width: Int, height: Int) {}

    override fun surfaceDestroyed(holder: SurfaceHolder) {
        isRunning = false
    }
}

```
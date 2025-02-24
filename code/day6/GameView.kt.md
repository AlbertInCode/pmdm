```kotlin
import android.content.Context
import android.graphics.Canvas
import android.graphics.Color
import android.graphics.Paint
import android.view.MotionEvent
import android.view.SurfaceHolder
import android.view.SurfaceView

class GameView(context: Context) : SurfaceView(context), SurfaceHolder.Callback {
    private val paint = Paint()
    private var ballX = 300f
    private var ballY = 300f
    private val ballRadius = 50f
    private var velocityX = 10f
    private var velocityY = 10f
    private var isPaused = false
    private var score = 0
    private val obstacles = mutableListOf<Obstacle>()

    init {
        holder.addCallback(this)
        // Create initial obstacles
        for (i in 0 until 3) {
            obstacles.add(
                Obstacle(
                    x = (800..1200).random().toFloat(),
                    y = (100..800).random().toFloat(),
                    width = 100f,
                    height = 100f,
                    speed = (5..10).random().toFloat()
                )
            )
        }
    }

    override fun surfaceCreated(holder: SurfaceHolder) {
        startGameLoop()
    }

    private fun startGameLoop() {
        Thread {
            while (true) {
                if (!isPaused) {
                    updatePhysics()
                    drawCanvas()
                }
                Thread.sleep(16) // ~60 FPS
            }
        }.start()
    }

    private fun updatePhysics() {
        ballX += velocityX
        ballY += velocityY

        if (ballX - ballRadius < 0 || ballX + ballRadius > width) velocityX = -velocityX
        if (ballY - ballRadius < 0 || ballY + ballRadius > height) velocityY = -velocityY

        // Update obstacles
        obstacles.forEach { it.update() }

        // Check collisions
        obstacles.forEach {
            if (it.checkCollision(ballX, ballY, ballRadius)) {
                isPaused = true // End game on collision
            }
        }

        // Increment score
        score++
    }

    private fun drawCanvas() {
        val canvas = holder.lockCanvas()
        canvas.drawColor(Color.BLACK)

        // Draw ball
        paint.color = Color.RED
        canvas.drawCircle(ballX, ballY, ballRadius, paint)

        // Draw obstacles
        obstacles.forEach { it.draw(canvas) }

        // Draw score
        paint.color = Color.WHITE
        paint.textSize = 50f
        canvas.drawText("Score: $score", 50f, 50f, paint)

        holder.unlockCanvasAndPost(canvas)
    }

    override fun onTouchEvent(event: MotionEvent): Boolean {
        if (event.action == MotionEvent.ACTION_DOWN) {
            isPaused = !isPaused // Toggle pause state
        }
        return true
    }

    override fun surfaceDestroyed(holder: SurfaceHolder) {}
    override fun surfaceChanged(holder: SurfaceHolder, format: Int, width: Int, height: Int) {}
}

```
```kotlin
import android.content.Context
import android.graphics.Canvas
import android.graphics.Paint
import android.view.SurfaceHolder
import android.view.SurfaceView

class GameView(context: Context) : SurfaceView(context), SurfaceHolder.Callback {
    private val paint = Paint()
    private val animations = Animations()
    private val soundManager = GameSoundManager(context)
    private var score = 0
    private var isPaused = false

    init {
        holder.addCallback(this)
        animations.animatePlayerPaint(paint)
    }

    override fun surfaceCreated(holder: SurfaceHolder) {
        startGameLoop()
    }

    private fun startGameLoop() {
        Thread {
            while (true) {
                if (!isPaused) {
                    updateGameLogic()
                    drawCanvas()
                }
                Thread.sleep(16)
            }
        }.start()
    }

    private fun updateGameLogic() {
        // Simulate score increment
        score++
        if (score % 10 == 0) soundManager.playScoreSound()

        // Simulate collision
        if (score == 50) {
            soundManager.playCollisionSound()
            isPaused = true
        }
    }

    private fun drawCanvas() {
        val canvas = holder.lockCanvas()
        canvas.drawColor(0xFF000000.toInt())
        paint.color = 0xFFFF0000.toInt()
        canvas.drawCircle(width / 2f, height / 2f, 50f, paint)
        holder.unlockCanvasAndPost(canvas)
    }

    override fun surfaceDestroyed(holder: SurfaceHolder) {
        soundManager.release()
    }

    override fun surfaceChanged(holder: SurfaceHolder, format: Int, width: Int, height: Int) {}
}

```
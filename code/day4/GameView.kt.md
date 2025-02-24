```kotlin
import android.animation.ValueAnimator
import android.content.Context
import android.graphics.Canvas
import android.graphics.Color
import android.graphics.Paint
import android.view.SurfaceHolder
import android.view.SurfaceView
import android.view.animation.AccelerateDecelerateInterpolator

class GameView(context: Context) : SurfaceView(context), SurfaceHolder.Callback {
    private val paint = Paint()
    private var ballX = 300f
    private var ballY = 300f
    private val ballRadius = 50f

    private var animator: ValueAnimator? = null

    init {
        holder.addCallback(this)
    }

    override fun surfaceCreated(holder: SurfaceHolder) {
        startAnimation()
    }

    private fun startAnimation() {
        animator = ValueAnimator.ofFloat(0f, width.toFloat()).apply {
            duration = 2000 // 2 seconds
            interpolator = AccelerateDecelerateInterpolator()
            addUpdateListener { animation ->
                ballX = animation.animatedValue as Float
                ballY = height / 2f // Keep the ball in the center vertically
                drawCanvas()
            }
            repeatCount = ValueAnimator.INFINITE
            repeatMode = ValueAnimator.REVERSE
            start()
        }
    }

    private fun drawCanvas() {
        val canvas = holder.lockCanvas()
        canvas.drawColor(Color.BLACK) // Clear screen

        paint.color = Color.RED
        canvas.drawCircle(ballX, ballY, ballRadius, paint)

        holder.unlockCanvasAndPost(canvas)
    }

    override fun surfaceDestroyed(holder: SurfaceHolder) {
        animator?.cancel()
    }

    override fun surfaceChanged(holder: SurfaceHolder, format: Int, width: Int, height: Int) {}
}

```
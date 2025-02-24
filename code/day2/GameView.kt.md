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
    private var touchX = 0f
    private var touchY = 0f

    init {
        holder.addCallback(this)
    }

    override fun surfaceCreated(holder: SurfaceHolder) {
        // Initialize the screen with a default message
        drawCanvas()
    }

    private fun drawCanvas() {
        val canvas = holder.lockCanvas()
        canvas.drawColor(Color.BLACK) // Clear the screen
        paint.color = Color.WHITE
        paint.textSize = 50f
        canvas.drawText("Touch the screen!", 100f, 100f, paint)

        // Draw a rectangle at the touch position
        paint.color = Color.RED
        canvas.drawRect(touchX - 50, touchY - 50, touchX + 50, touchY + 50, paint)

        holder.unlockCanvasAndPost(canvas)
    }

    override fun onTouchEvent(event: MotionEvent): Boolean {
        if (event.action == MotionEvent.ACTION_DOWN || event.action == MotionEvent.ACTION_MOVE) {
            touchX = event.x
            touchY = event.y
            drawCanvas()
        }
        return true
    }

    override fun surfaceChanged(holder: SurfaceHolder, format: Int, width: Int, height: Int) {}

    override fun surfaceDestroyed(holder: SurfaceHolder) {}
}
```

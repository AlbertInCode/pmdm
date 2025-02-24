```kotlin
import android.content.Context
import android.graphics.Canvas
import android.graphics.Color
import android.graphics.Paint
import android.view.SurfaceHolder
import android.view.SurfaceView

class GameView(context: Context) : SurfaceView(context), SurfaceHolder.Callback {
    private val paint = Paint()

    init {
        holder.addCallback(this)
    }

    override fun surfaceCreated(holder: SurfaceHolder) {
        val canvas = holder.lockCanvas()
        canvas.drawColor(Color.BLACK)
        paint.color = Color.WHITE
        paint.textSize = 50f
        canvas.drawText("Hello, Game World!", 100f, 100f, paint)
        holder.unlockCanvasAndPost(canvas)
    }

    override fun surfaceChanged(holder: SurfaceHolder, format: Int, width: Int, height: Int) {
        // Handle changes here if needed
    }

    override fun surfaceDestroyed(holder: SurfaceHolder) {
        // Clean up resources
    }
}
```
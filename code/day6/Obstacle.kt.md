```kotlin
import android.graphics.Canvas
import android.graphics.Color
import android.graphics.Paint

class Obstacle(
    private var x: Float,
    private var y: Float,
    private val width: Float,
    private val height: Float,
    private val speed: Float
) {
    private val paint = Paint().apply { color = Color.YELLOW }

    fun update() {
        x -= speed
        if (x + width < 0) {
            x = (1000..1200).random().toFloat() // Reset position
            y = (100..800).random().toFloat()
        }
    }

    fun draw(canvas: Canvas) {
        canvas.drawRect(x, y, x + width, y + height, paint)
    }

    fun checkCollision(ballX: Float, ballY: Float, ballRadius: Float): Boolean {
        val closestX = x.coerceAtLeast(ballX.coerceAtMost(x + width))
        val closestY = y.coerceAtLeast(ballY.coerceAtMost(y + height))
        val distanceX = ballX - closestX
        val distanceY = ballY - closestY
        return (distanceX * distanceX + distanceY * distanceY) < (ballRadius * ballRadius)
    }
}

```
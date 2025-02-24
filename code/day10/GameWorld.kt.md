```kotlin
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import android.widget.TextView

class GameWorld : AppCompatActivity() {
    private lateinit var player: Player
    private lateinit var scoreTextView: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_game_world)

        player = Player()
        scoreTextView = findViewById(R.id.scoreTextView)

        // Example of collecting a power-up item
        val speedBoostItem = PowerUpItem(PowerUp.SpeedBoost, 50f, 100f)
        speedBoostItem.onCollision(player)

        // Display current speed
        scoreTextView.text = "Speed: ${player.speed}"
    }
}

```
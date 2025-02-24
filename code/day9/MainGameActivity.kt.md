```kotlin
import android.content.Intent
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import android.widget.TextView

class MainGameActivity : AppCompatActivity() {
    private lateinit var scoreTextView: TextView
    private var score = 0

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main_game)

        scoreTextView = findViewById(R.id.scoreTextView)

        // Example game logic to update score
        score++
        scoreTextView.text = "Score: $score"
    }

    private fun endGame() {
        val intent = Intent(this, GameOverScreen::class.java).apply {
            putExtra("SCORE", score)
        }
        startActivity(intent)
    }
}

```
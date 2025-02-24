```kotlin
import android.content.Context
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import android.widget.TextView

class GameOverScreen : AppCompatActivity() {
    private lateinit var scoreManager: ScoreManager
    private lateinit var scoreTextView: TextView
    private lateinit var leaderboardTextView: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_game_over)

        scoreManager = ScoreManager(this)
        scoreTextView = findViewById(R.id.scoreTextView)
        leaderboardTextView = findViewById(R.id.leaderboardTextView)

        val score = intent.getIntExtra("SCORE", 0)
        scoreManager.saveScore(score)

        scoreTextView.text = "Your Score: $score"
        displayLeaderboard()
    }

    private fun displayLeaderboard() {
        val topScores = scoreManager.loadScores()
        leaderboardTextView.text = "Top Scores:\n${topScores.joinToString("\n")}"
    }
}

```
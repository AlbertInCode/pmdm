```kotlin
import android.content.Context

class GameEngine(private val context: Context) {
    private val progressManager = GameProgressManager(context)
    private var currentLevel = Level(1, 2f, 10)
    private var score = 0

    fun initGame() {
        val savedProgress = progressManager.loadProgress()
        currentLevel = Level(savedProgress.first, 2f * savedProgress.first, 10 * savedProgress.first)
        score = 0
    }

    fun updateGameLogic() {
        score++
        if (score >= currentLevel.scoreThreshold) {
            advanceLevel()
        }
    }

    private fun advanceLevel() {
        currentLevel = Level(
            currentLevel.levelNumber + 1,
            currentLevel.obstacleSpeed * 1.2f,
            currentLevel.scoreThreshold + 10
        )
        progressManager.saveProgress(currentLevel.levelNumber, score)
    }
}

```
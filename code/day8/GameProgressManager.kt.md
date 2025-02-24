```kotlin
import android.content.Context
import android.content.SharedPreferences

class GameProgressManager(context: Context) {
    private val preferences: SharedPreferences =
        context.getSharedPreferences("GameProgress", Context.MODE_PRIVATE)

    fun saveProgress(level: Int, highScore: Int) {
        preferences.edit().apply {
            putInt("currentLevel", level)
            putInt("highScore", highScore)
            apply()
        }
    }

    fun loadProgress(): Pair<Int, Int> {
        val level = preferences.getInt("currentLevel", 1)
        val highScore = preferences.getInt("highScore", 0)
        return Pair(level, highScore)
    }
}

```
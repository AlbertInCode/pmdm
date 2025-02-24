```kotlin
import android.content.Context
import android.content.SharedPreferences

class ScoreManager(context: Context) {
    private val preferences: SharedPreferences =
        context.getSharedPreferences("GameScores", Context.MODE_PRIVATE)

    fun saveScore(score: Int) {
        val topScores = loadScores().toMutableList()
        topScores.add(score)
        topScores.sortDescending()

        if (topScores.size > 5) {
            topScores.removeAt(5)  // Keep only top 5 scores
        }

        preferences.edit().apply {
            putStringSet("topScores", topScores.map { it.toString() }.toSet())
            apply()
        }
    }

    fun loadScores(): List<Int> {
        return preferences.getStringSet("topScores", setOf())?.map { it.toInt() } ?: emptyList()
    }
}

```
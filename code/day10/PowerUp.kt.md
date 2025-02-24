```kotlin
// Power-up item class
sealed class PowerUp(val effectDuration: Long) {
    object SpeedBoost : PowerUp(5000) // 5 seconds boost
    object Shield : PowerUp(8000) // 8 seconds shield
    object Invincibility : PowerUp(10000) // 10 seconds invincibility
    object ScoreMultiplier : PowerUp(7000) // 7 seconds multiplier

    abstract fun activateEffect(player: Player)
}

// Example Power-up Logic
class Player {
    var speed: Float = 1f
    var isShieldActive: Boolean = false
    var isInvincible: Boolean = false
    var scoreMultiplier: Int = 1

    fun activatePowerUp(powerUp: PowerUp) {
        when (powerUp) {
            is PowerUp.SpeedBoost -> {
                speed *= 2 // Double speed
                // Set a timer to reset the speed after effectDuration
            }
            is PowerUp.Shield -> {
                isShieldActive = true
                // Set a timer to deactivate the shield after effectDuration
            }
            is PowerUp.Invincibility -> {
                isInvincible = true
                // Set a timer to deactivate invincibility after effectDuration
            }
            is PowerUp.ScoreMultiplier -> {
                scoreMultiplier = 2 // Double the score for a limited time
                // Set a timer to reset the multiplier after effectDuration
            }
        }
    }
}

```
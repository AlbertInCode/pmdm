```kotlin
// Power-up item class used in the game world
class PowerUpItem(val type: PowerUp, val x: Float, val y: Float) {
    fun onCollision(player: Player) {
        // If the player collides with the power-up item, activate its effect
        player.activatePowerUp(type)
    }
}

```
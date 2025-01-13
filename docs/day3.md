# Day 3: Adding Physics to Your Game

## Introduction

Today, we’ll bring your game objects to life by incorporating basic physics principles. You’ll learn how to:
1. Simulate movement.
2. Handle boundaries (e.g., screen edges).
3. Add gravity for a realistic effect.

---

## Understanding Physics in Games

Physics in games simplifies real-world principles into manageable rules. Core concepts include:
- **Velocity**: Speed in a particular direction.
- **Gravity**: A force pulling objects downward.
- **Collision Detection**: Determining when objects interact.

In this session, we’ll apply these concepts to a bouncing ball simulation.

---

## Step-by-Step Instructions

### Step 1: Extend `GameView`

1. Add variables for the ball's position, velocity, and radius.
2. Update the `drawCanvas` method to draw a ball at the current position.
3. Add a game loop to update the ball’s position over time.

Refer to the external code file `GameView.kt`.

---

### Step 2: Handle Screen Boundaries

Modify the game logic to:
1. Reverse the ball’s velocity when it hits the screen edges.
2. Gradually reduce velocity to simulate friction.

---

## Practice Exercise

Expand the program to:
1. Add a second ball with its own velocity and movement logic.
2. Detect and respond to collisions between the two balls.

Hints:
- Use the distance formula to detect collisions:

```
distance = sqrt((x2 - x1)^2 + (y 2 - y1)^2)
```

- Reverse velocities upon collision.

---

## Summary

Today, you learned:
1. How to simulate movement using velocity.
2. How to handle boundaries and collisions.
3. How to implement simple physics in your game.

---

## References

- [Canvas.drawCircle Documentation](https://developer.android.com/reference/android/graphics/Canvas#drawCircle)
- Tutorials on physics simulation in Android games.

---

# Next Steps

In the next session, we’ll enhance the game by incorporating animations for smoother transitions. Get ready for a visually dynamic experience!

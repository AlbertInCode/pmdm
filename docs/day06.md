# Day 6: Scoring System and Obstacles

## Introduction

Today we will make your game more engaging by:
1. Adding a scoring system.
2. Introducing obstacles that the player must avoid.
3. Combining these features to increase the challenge.

---

## Scoring System

A scoring system is a fundamental game mechanic to measure player progress. Key steps:
- Initialize a score variable.
- Increment the score as the player survives or interacts with the game.
- Display the score on the screen.

---

## Adding Obstacles

Obstacles create challenges and keep the game exciting. We will:
1. Create simple rectangular obstacles.
2. Randomize their position and movement.
3. Detect collisions with the player.

---

## Step-by-Step Instructions

### Step 1: Implement the Scoring System

1. Add a `score` variable in `GameView`.
2. Increment the score periodically as the game runs.
3. Use `Canvas` to display the score on the screen.

---

### Step 2: Create Obstacles

1. Define an `Obstacle` class to represent obstacles.
2. Randomize the position and speed of obstacles.
3. Update their position in the game loop.

---

### Step 3: Detect Collisions

1. Check for overlap between the ball and obstacles.
2. End the game if a collision occurs.
3. Allow restarting the game after a collision.

---

## Practice Exercise

Enhance the program by:
1. Adding multiple obstacles with varying speeds.
2. Increasing the game difficulty as the score increases.
3. Providing visual feedback (e.g., flashing colors) when a collision happens.

---

## Summary

Today, you implemented:
1. A scoring system to track player progress.
2. Dynamic obstacles to increase the game’s difficulty.
3. Collision detection to challenge the player.

---

## References

- [Canvas Drawing Documentation](https://developer.android.com/reference/android/graphics/Canvas)
- Tutorials on scoring and collision detection in games.

---

# Next Steps

In the next session, we’ll add animations and sound effects to enhance the game’s feedback and immersion. Get ready to bring your game to life!

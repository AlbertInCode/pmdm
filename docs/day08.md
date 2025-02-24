# Day 8: Managing Game Levels and Difficulty Progression

## Introduction

As games progress, they should become more challenging to keep players engaged. Today, we will:
1. Implement a system to manage levels.
2. Increase difficulty based on player performance.
3. Save and restore player progress using `SharedPreferences`.

---

## Game Levels

Levels introduce variety and excitement. We will:
1. Create distinct levels with increasing complexity.
2. Define criteria for advancing between levels (e.g., score thresholds).

---

## Difficulty Progression

Make the game more challenging by:
1. Increasing obstacle speed.
2. Adding more obstacles dynamically.
3. Introducing level-specific rules.

---

## Saving Progress

To ensure players can resume their progress:
1. Use `SharedPreferences` to save the current level and score.
2. Load saved data when the game starts.

---

## Step-by-Step Instructions

### Step 1: Create Levels

1. Define a `Level` class with properties like obstacle speed and score threshold.
2. Implement logic to switch levels.

---

### Step 2: Adjust Difficulty Dynamically

1. Increase obstacle speed as levels progress.
2. Randomize obstacle patterns for higher levels.

---

### Step 3: Save and Load Progress

1. Use `SharedPreferences` to store:
   - Current level
   - High score
2. Automatically load saved progress when the game restarts.

---

## Practice Exercise

Enhance the game by:
1. Adding a menu screen to select levels or start a new game.
2. Implementing a visual indicator (e.g., a banner) when the player advances to the next level.
3. Creating at least three distinct levels with unique rules or visuals.

---

## Summary

Today, you learned to:
1. Implement a level-based structure for your game.
2. Dynamically adjust difficulty to challenge players.
3. Save and restore progress using `SharedPreferences`.

---

## References

- [SharedPreferences Documentation](https://developer.android.com/training/data-storage/shared-preferences)
- [Android Game Development Guide](https://developer.android.com/games)

---

# Next Steps

In the next session, we’ll focus on creating a scoring system and leaderboards. Get ready to add a competitive edge to your game!

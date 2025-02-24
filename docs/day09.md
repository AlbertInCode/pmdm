# Day 9: Implementing a Scoring System and Leaderboards

## Introduction

A scoring system is essential in game development, and leaderboards add a competitive aspect that can motivate players. Today, we will:
1. Create a scoring system that tracks the player’s progress.
2. Implement a local leaderboard using `SharedPreferences`.
3. Display the top scores for a competitive edge.

---

## Scoring System

Scoring adds incentive for players to improve. We will:
1. Define how the score is updated (e.g., based on time, enemies defeated, or obstacles avoided).
2. Display the score in real-time on the screen.

---

## Leaderboards

Leaderboards help create competition among players. We will:
1. Store top scores in a local leaderboard using `SharedPreferences`.
2. Display the leaderboard in the game.

---

## Saving and Displaying Scores

1. Save the score every time the player finishes a level or reaches a milestone.
2. Keep track of the top 5 scores locally.
3. Display the leaderboard when the player completes the game.

---

## Step-by-Step Instructions

### Step 1: Define the Scoring System

1. Track the score based on in-game events (e.g., time elapsed, enemies defeated).
2. Display the current score in a text field on the UI.

---

### Step 2: Create a Leaderboard

1. Define a data structure to store the leaderboard (e.g., a list of top scores).
2. Save the top 5 scores to `SharedPreferences`.
3. Load and display the top scores when the player completes a game session.

---

### Step 3: Save and Display Scores

1. Use `SharedPreferences` to save:
   - Player's score at the end of the game.
   - The top 5 scores.
2. Display the top scores in a leaderboard screen.

---

## Practice Exercise

Enhance the game by:
1. Implementing a “Game Over” screen that displays the player’s score.
2. Storing and displaying the top 5 scores.
3. Adding a “Retry” button to allow players to replay the game.

---

## Summary

Today, you learned to:
1. Implement a dynamic scoring system based on in-game events.
2. Create a leaderboard using `SharedPreferences` to store top scores.
3. Display the leaderboard for a competitive experience.

---

## References

- [SharedPreferences Documentation](https://developer.android.com/training/data-storage/shared-preferences)
- [Game Design Best Practices](https://www.gamasutra.com/)

---

# Next Steps

In the next session, we’ll introduce special power-ups and items to boost the gameplay experience. Prepare for some exciting gameplay mechanics!

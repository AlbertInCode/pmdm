# Day 1: Understanding Game Development Basics

## Introduction

Welcome to your first step into Android game development with Kotlin! Today, we’ll cover the foundational concepts of game development and set up your first project. By the end of this session, you'll understand the game loop mechanism and create a simple `SurfaceView` to draw on the screen.

## What is a Game Loop?

The **game loop** is the core of any game. It’s a programming construct that ensures the game continuously updates the game state and renders graphics on the screen. Here's a simplified flow:

1. **Process Input**: Detect user interactions, like taps or swipes.
2. **Update**: Change the game state based on logic or physics.
3. **Render**: Draw the updated state on the screen.

This loop runs repeatedly, creating a smooth and interactive experience.

### Game Loop in Pseudocode
```
 while (gameIsRunning):
 	processInput()
 	updateGameState()
 	renderGraphics()
```


This logic is implemented in Android using a `SurfaceView` and a thread for rendering.

---

## Setting Up Your First Android Game Project

To get started:

1. Open **Android Studio** and create a new **Empty Activity** project.
2. Configure the project:
   - Language: Kotlin
   - Minimum SDK: API 21 (Android 5.0)
3. Name the project `GameBasics`.

After the project is created, we'll set up a `SurfaceView` to handle custom drawing.

---

## Implementing a SurfaceView

### Step 1: Create a Custom View

Follow the steps below:

1. Create a new Kotlin class named `GameView`.
2. Add the following code (refer to the external file `GameView.kt`).
3. Update your `MainActivity` to use the `GameView` class. See the file `MainActivity.kt`.

---

## Practice Exercise

Your task:
1. Modify the `GameView` class to draw a rectangle that changes position each time you touch the screen.
2. Hints:
   - Use `MotionEvent` to detect touch input.
   - Call `invalidate()` to trigger a redraw of the view.

---

## Summary

Today, you learned:
1. The basics of the game loop.
2. How to set up a custom `SurfaceView` in Android.
3. How to draw on the screen using the `Canvas` API.

These concepts are the building blocks for creating games on Android. In the next session, we’ll dive into **input handling** to make your game interactive.

---

## References

- [Android Canvas API](https://developer.android.com/reference/android/graphics/Canvas)
- [SurfaceView Documentation](https://developer.android.com/reference/android/view/SurfaceView)
- Tutorials on basic game loops in Android.

---

# Next Steps

In the next chapter, we’ll add interactivity to your game by handling user input, including touch gestures. Stay tuned!

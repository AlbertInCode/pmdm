# Day 2: Adding Interactivity - Handling User Input

## Introduction

Welcome to Day 2 of your game development journey! Today, we’ll focus on adding interactivity to your game. You’ll learn how to handle user input, such as touch events, and modify your game logic in response.

## Understanding Touch Events

In Android, user input is handled using **MotionEvent**. The most common touch actions include:
- **ACTION_DOWN**: The user touches the screen.
- **ACTION_MOVE**: The user moves their finger on the screen.
- **ACTION_UP**: The user lifts their finger off the screen.

By overriding the `onTouchEvent` method, you can detect and respond to these actions.

---

## Updating Your Game

### Task Overview

Today, you'll extend your `GameView` to:
1. Detect touch input.
2. Move a rectangle to the touch position.
3. Redraw the screen with the updated position.

---

## Step-by-Step Instructions

### Step 1: Modify `GameView`

1. Add variables to store the rectangle’s position.
2. Override the `onTouchEvent` method to capture touch coordinates.
3. Call `invalidate()` to trigger a redraw of the `SurfaceView`.

Refer to the updated code in `GameView.kt`.

---

## Step 2: Visual Feedback

Add logic to draw a rectangle at the touch position:
- Use the `Canvas.drawRect` method.
- Clear the screen before redrawing by using `Canvas.drawColor`.

---

## Practice Exercise

Modify the program to:
1. Draw multiple rectangles on the screen, keeping track of all touch points.
2. Clear the screen when a double-tap gesture is detected.

Hints:
- Use a `List<Pair<Float, Float>>` to store touch points.
- Detect double-tap gestures using `GestureDetector`.

---

## Summary

Today, you learned:
1. How to handle user input using `MotionEvent`.
2. How to update the game state based on touch events.
3. How to render interactive elements on the screen.

---

## References

- [MotionEvent Documentation](https://developer.android.com/reference/android/view/MotionEvent)
- [GestureDetector Guide](https://developer.android.com/reference/android/view/GestureDetector)
- Tutorials on handling touch input in Android.

---

# Next Steps

In the next session, we’ll add more complexity by incorporating physics-based movement. Get ready to see your objects come to life!

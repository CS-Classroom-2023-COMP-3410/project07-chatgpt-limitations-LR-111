### **Overview**
The goal for this part of the project was to ensure that the memory game was **fully responsive** while keeping the **dancing fruit border fully visible** at all times. The original issue was that when resizing the window—particularly in wide or short screens—the game grid would **extend beyond the viewport**, making it unplayable and requiring scrolling. 

This issue has now been fixed by:
1. **Ensuring the game container always fits inside the viewport without scrolling.**
2. **Maintaining proportional scaling of the game grid and cards so they remain playable at any screen size.**
3. **Leaving enough space at the top and bottom so the dancing fruit border is never obstructed.**

---

### **What Changed**
1. **Centered and Scaled the Game Container Dynamically**
   - Previously, the `.game-container` had a fixed width (`min(90vw, 600px)`) which caused it to **overflow** on smaller screens.
   - It has now been modified to **always fit within the viewport** using:
     ```css
     width:  min(calc(100vw - 100px), calc(100vh - 100px));
     height: min(calc(100vw - 100px), calc(100vh - 100px));
     ```
   - This ensures the game **never** gets larger than the available space, while keeping the fruit border fully visible.
   - The `100px` value leaves enough **margin around the game box** so fruit animations are never obstructed.

2. **Made the Game Grid and Cards Scale Proportionally**
   - The `.grid` was adjusted so that **each card remains a perfect square**, regardless of screen size:
     ```css
     grid-template-columns: repeat(4, 1fr);
     grid-template-rows: repeat(4, 1fr);
     ```
   - This means the entire grid shrinks or expands **while keeping all cards evenly spaced and proportionally sized**.

3. **Prevented Scrolling & Ensured Full Visibility of Fruit Border**
   - The page no longer requires **scrolling**, thanks to:
     ```css
     overflow: hidden;
     ```
   - This ensures that **both the game and the fruit border fit within the screen at all times**.

4. **Adjusted Margin to Prevent Game Box from Overlapping Dancing Fruits**
   - The `.game-container` was initially **slightly covering the top and bottom fruit decorations**.
   - We **increased** the margin subtracted from the viewport (`100px` instead of `80px`) so that the game box has enough breathing room.

---

### **Final Outcome**
- The game now **automatically resizes** to fit any **reasonable screen size**, while keeping the **fruit border fully visible**.
- The **grid and cards scale proportionally** so they remain playable on all screens.
- There is **no more scrolling**, and **no part of the UI gets cut off**.

These changes successfully implemented the intended **responsive** behavior while preserving all original game functionality.

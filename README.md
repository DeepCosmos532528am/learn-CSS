  # Learn CSS

  Mastering CSS (Cascading Style Sheets)  
  Your complete resource for learning web styling – featuring hands-on examples, modern techniques like Flexbox and Grid, and projects ranging from foundational concepts to advanced responsive layouts.

  ---

  ## ✅ Topics Covered So Far

  ### Day 1 – CSS Fundamentals

  1. **Inline CSS**
  2. **Internal CSS**
  3. **External CSS** (Recommended)
  4. `color` – Text color
  5. `background-color` – Background shading
  6. **Selectors**:
    - Tag selector (`div`, `p`, `h1`)
    - ID selector (`#id`)
    - Class selector (`.class`)
    - Group selectors (`div, p, .class, #id`)
  7. `font-size` – Text sizing
  8. **CSS Units**: `px`, `em`, `rem`, `%`, `vw`, `vh`
  9. `font-family` – Choosing fonts
  10. `font-weight` – Boldness
  11. `font-style` – Italic, oblique

  ---

  ### Day 2 – Box Model and Elements

  12. `height`
  13. `width`
  14. `padding` – Inner spacing
  15. `margin` – Outer spacing
  16. `border` – Outline around elements
  17. `font-style` (revisited)
  18. `box-shadow` – Shadow effects
  19. `<span>` – Inline text container
  20. `*` – Universal selector to target all elements  
  21. Block-Level vs Inline Elements

      Block elements form the main structure of a page. They always start on a new line and take up the full width available by default.

      **Characteristics:**
      - Start on a new line
      - Take full width of the parent container
      - Width and height can be set
      - Respect all margins and padding

      **Examples:**

      ```html
      <div>, <p>, <h1>-<h6>, <ul>, <ol>, <li>, <section>, <article>, <header>, <footer>
      ```

      Inline elements flow along with text and only take up as much width as necessary.

      **Characteristics:**
      - Do not start on a new line
      - Only as wide as their content
      - Cannot set width or height directly
      - Only respect horizontal spacing

      **Examples:**

      ```html
      <span>, <a>, <strong>, <em>, <img>
      ```

  22. `display:inline` for making the block element to inline element.
  No vertical styling like height, top etc types works on inlines then.

  23. `display:block`for making the inline to behave as block element. (vice-versa of display:inline)

  24. `display:inline` for combining the best features of the inline and block on any element

  25. `box-sizing` controls how the browser calculates the total width and height of an element.

  26. `box-sizing:content-box` Default.Padding and border are added outside, increasing total size.

  27. `box-sizing:border-box`(recommended and mostly used) Width/height apply to content + padding + border all together. Total size stays as set.

  ### Day 4 – Positioning, Stacking & Viewport Concepts

  28. `CSS Priority and Specificity` – Understanding the Myth

  ## CSS Priority: Inline > Internal > External (Half Myth!)

  This is only **half true**. The **actual priority or affection of CSS rules** does **not** solely depend on where the CSS is written (inline, internal, external), but rather on **which rule comes later** (in the cascade), **and the specificity** of the selector used.

  Think of CSS as checking rooms in a line:

  - You have **10 rooms** to check.
  - You must go **sequentially from Room 1 to Room 10**.
  - **You cannot go back** or **break the sequence**.
  - After visiting all rooms, **you choose the room with the most money to stay in**.

  In this analogy:

  - The **room number** represents the **order of CSS in the document**.
  - The **money in the room** represents the **selector specificity** or the **way CSS is applied**.

  ### Selector Specificity (Money in the Room)

  | Selector Type | Specificity (Money) | Notes                            |
  |---------------|---------------------|----------------------------------|
  | Inline CSS    | ₹1000               | Highest specificity              |
  | ID Selector   | ₹700                | High specificity (`#id`)        |
  | Class Selector| ₹500                | Medium specificity (`.class`)   |
  | Tag Selector  | ₹200                | Lowest specificity (`div`, `p`) |

  Even if a `tag selector` comes later in the cascade, an earlier `ID selector` or `inline style` might **win** due to higher specificity.

  So, **order (cascade) is important**, but **selector specificity (money) decides who actually wins**.
          ----
  29. `!important` Flag – Top Priority Override

  If a CSS rule includes the `!important` flag, it **overrides all other rules**, regardless of specificity or order.

  ```css
      p {
      color: red !important;
      }    
  ```

  ⚠️ Use `!important` sparingly. It breaks the natural cascade and can make debugging CSS difficult.

  30. CSS Position Property – Controlling Element Flow

  The `position` property determines how an element is placed in the document flow. Main values:

  - `static` (default): In normal flow, cannot use `top`, `left`, etc.
  - `relative`: In flow, but can be nudged visually using `top`, `left`, etc.
  - `absolute`: Removed from flow, positioned relative to nearest positioned ancestor.
  - `fixed`: Removed from flow, positioned relative to the viewport (screen).
  - `sticky`: Behaves like `relative` until a scroll threshold, then acts like `fixed`.

  📌 Absolute, fixed, and sticky are out of the normal flow. Relative and static are in the flow.

  ---

  31. CSS Z-Index – Layering Elements

      The `z-index` property controls the stacking order of positioned elements.

      - Higher `z-index` = appears on top
      - Only works on elements with `position` set to `relative`, `absolute`, `fixed`, or `sticky`

      ```css
      .box1 {
        position: relative;
        z-index: 10;
      }
      .box2 {
        position: relative;
        z-index: 5;
      }
      ```

      📌 Default stacking: later elements appear on top unless z-index says otherwise.

  ---

  32. Viewport – What You See

      The viewport is the **visible area** of the web page — what fits inside the browser window.

      - Units like `vw` (viewport width) and `vh` (viewport height) relate to this area
      - Elements with `position: fixed` are stuck to the viewport and don't scroll with the page

      📌 Viewport ≠ entire page. It’s just the “window” through which we view the page.

  ---

  33. Scroll Behavior & Flow Impact

      Only elements in the **normal document flow** contribute to page height and scrolling.

      - `relative` and `static` elements add height → scrollable
      - `absolute` and `fixed` elements do **not** → no scroll added unless inside a scrollable container

      📌 If your page doesn’t scroll, check if you’re using too many fixed/absolute elements.

  ---

  34. Practical Use of Positioning in Real Projects

      ✅ Common use cases:
      - `relative`: as a positioning context or slight adjustment
      - `absolute`: tooltips, dropdowns, badges, floating elements
      - `fixed`: sticky navbars, back-to-top buttons, modals
      - `sticky`: headers that stick on scroll (e.g., table headers)

      ⚠️ Use positioning intentionally. Avoid layout bugs by understanding flow and stacking.

  ---

  35. Projects Built Using Positioning Concepts

      - 🇫🇷 Contriex Flag: Used `absolute` and `relative` to position colored blocks correctly
      - 🎯 Sticky Navbar UI: Demonstrated `sticky` and `fixed` in scrollable layout
      - 💬 Tooltip Component: Built using `position: absolute` inside a `relative` parent
      - 🪟 Modal Popup: Centered using `fixed` + `transform: translate(-50%, -50%)`

      📌 These helped apply `z-index`, flow rules, and viewport logic practically.

  ---

  ### Day 4 – Positioning, Stacking & Viewport Concepts

  36. **`display: flex`**

      - Applied on the **parent container**, flexbox affects how **child elements** are laid out.
      - Enables flexible and responsive layouts.

  37. **Main Axis and Cross Axis**

      - Flexbox layouts have two axes:
      - **Main axis**: Direction defined by `flex-direction` (`row` or `column`).
      - **Cross axis**: Perpendicular to the main axis.
    
  38. **`justify-content`**

      - Aligns children **along the main axis**.
      - Common values:
      - `flex-start` (default)
      - `center`
      - `flex-end`
      - `space-between`
      - `space-around`
      - `space-evenly`

  39. **`align-items`**

      - Aligns children **along the cross axis**.
      - Common values:
      - `stretch` (default)
      - `center`
      - `flex-start`
      - `flex-end`
      - `baseline`

  40. **Flex Properties on Children**

      - `flex-grow`: Defines how much a flex item will grow relative to others.
      - `flex-shrink`: Defines how much a flex item will shrink relative to others.
      - `flex-basis`: Sets the initial main size of a flex item before growing or shrinking.
      - `align-self`: Overrides `align-items` for individual items.

  41. **Flex Wrap & Gap**

      - `flex-wrap: wrap;` allows flex items to wrap onto multiple lines.
      - `gap` creates spacing between flex items easily without margins.

  42. **Practical Notes**

      - Flexbox simplifies layout tasks like centering, spacing, and ordering elements.
      - It replaces many older layout hacks involving floats and positioning.
      - Experiment with `flex-direction`, `justify-content`, `align-items`, and flex child properties to control layout precisely.

      ---

      #### Example Summary from Today's Practice

      ```css
      #container {
          display: flex;
          flex-direction: row;
          gap: 20px;
          height: 700px;
          width: 100%;
      }

          #f { background-color: antiquewhite; }
          #s { background-color: aqua; flex-shrink: 2; }
          #t { background-color: blueviolet; align-self: flex-end; }
          #fo { background-color: brown; flex-basis: 120px; }
          #fi { background-color: burlywood; }
          
  43. **Responsive Behavior with Flexbox**

      - Flex items automatically adjust their size and position to fit different screen sizes.
      - Using `flex-wrap: wrap` lets items flow into multiple rows or columns on smaller screens.
      - Combining `flex-grow`, `flex-shrink`, and `flex-basis` allows flexible and adaptive layouts without media queries in many cases.

          ---
  44. **made Login & Signup form**

  ### Day 5 – CSS Grid Layout  

  45. **Introduction to Grid** – `display: grid;` turns a container into a grid parent. Child elements (grid items) are placed inside defined **rows** and **columns**. Compared to Flexbox: Flexbox is 1D (row OR column), Grid is 2D (rows AND columns at the same time).  

  46. **Defining Rows and Columns** – `grid-template-rows` defines row sizes, `grid-template-columns` defines column sizes. Units can be `px`, `%`, `fr`, or `auto`. Example:  

      ```css
      .container {
      display: grid;
      grid-template-rows: 200px 200px;
      grid-template-columns: 200px 200px;
      }

  - 📌 fr = “fractional unit” → best for flexible, responsive grids.

  47. **Gap Between Items**
      - gap adds spacing between rows and columns.

  Shorthand for row-gap + column-gap.

  ```css
      .container {
        display: grid;
          gap: 10px;
      }
  ```

  48. **Repeat Function**

      - Shortcut for repeating row/column sizes.

      ```css
      grid-template-columns: repeat(8, 1fr);
      grid-template-rows: repeat(8, 1fr);
      ```

      - 📌 Used in making a chessboard layout.

  49. **Placing Items with Grid Lines**

      grid-column and grid-row place elements precisely.

      ```css
      /* Syntax: grid-column: start / end; */

      .green1 {
        grid-row: 1 / 4; /* spans 3 rows */
      }
      .green2 {
        grid-column: 2 / 4; /* spans across 2 columns */
      }
      ```

  50. **Spanning Rows & Columns**

      Grid items can stretch over multiple rows/columns.

      ```css
      .header {
        grid-column: 1 / 4; /* span across 3 columns */
      }
      .sidebar {
        grid-row: 2 / 4;   /* span across 2 rows */
      }
      ```

  51. **Responsive Units in Grid**

      - fr (fraction): flexible division of free space.

      - minmax(min, max): set min and max size.

      - auto-fit & auto-fill: let grid auto-create tracks.

      ```css
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      ```

  52. **Nested Grids**

      - A grid item can itself become a grid container.

      - Useful for complex layouts (e.g., dashboard → sidebar with its own sections).

      ```css
      .row2-col2 {
        display: grid;
        grid-template-rows: 50fr 50fr;
      }
      ```

  53. **Grid vs Flexbox – When to Use?**

      - Flexbox → perfect for linear layouts (navbars, toolbars, aligning buttons).

      - Grid → perfect for 2D layouts (page templates, dashboards, games like chess).

      - They can be combined in real projects.

  54. **Practical Layouts Built**

      ✅ 2×2 grid with fractional units.

      ✅ Chessboard (8×8 grid) using repeat(8, 1fr).

      ✅ Complex green/red/yellow grid (L-shaped spans).

      ✅ Website template with header, sidebar, content, footer.

      ✅ Nested grids for advanced responsive layout.

  55. **Project Ideas with Grid**

      - Chessboard UI

      - Calculator layout

      - Portfolio gallery

      - Dashboard with sidebar & widgets

      - News website (header, nav, content, footer)

  ### Day 6 - Website Responsiveness | Media Queries, Overflow, Box Shadows  

  56. **What is a Responsive Website?**  
      - A responsive website adjusts its layout and content based on the screen size or device.  
      - It ensures readability and usability on mobiles, tablets, laptops, and desktops.  
      - Achieved using fluid grids, flexible images, and media queries.

  57. **How to Create a Responsive Website**  
      - Start with a mobile-first approach.  
      - Use percentage-based widths or `fr` units for flexible grids.  
      - Apply media queries to adapt layout at breakpoints (e.g., tablet, desktop).  
      - Test across different screen sizes and orientations.

  58. **Example Walkthrough**  
      ✅ Base mobile layout using stacked elements  
      ✅ Add breakpoints at 768px and 1024px  
      ✅ Use `flex` or `grid` at larger sizes  
      ✅ Adjust font sizes and spacing at each stage  

      ```css
      @media (min-width: 768px) { ... }
      @media (min-width: 1024px) { ... }
      ```

  59. **Understanding Media Queries**  
      - Media queries let CSS apply rules conditionally based on device characteristics.  
      - Syntax: `@media (min-width: 768px) { ... }`  
      - Common conditions: `min-width`, `max-width`, `orientation`, `resolution`.

  60. **The `screen` Keyword**  
      - Specifies that the styles apply to screens only (not print).  
      - Often omitted in modern responsive design as `screen` is the default.  

      ```css
      @media screen and (min-width: 1024px) { ... }
      ```

  61. **Removing Fixed Height and Width**  
      - Avoid hardcoded `width` and `height` like `width: 1200px`.  
      - Use flexible units: `%`, `vw`, `fr`, `minmax()`.  
      - Let containers adapt to content or screen size.

  62. **Using `min-width` in Media Queries**  
      - Triggers styles when the viewport is **at least** a certain width.  
      - Key to **mobile-first** development.  
      - Ensures styles are **progressively enhanced** as screen grows.  

      ```css
      @media (min-width: 768px) { ... }
      ```

  63. **Key Concept Explained**  
      - Start small → build up.  
      - Default/mobile styles first.  
      - Layer enhancements for larger screens via `min-width`.  
      - This avoids code repetition and ensures better performance on mobile.

  64. **Mobile-First vs Desktop-First Approach**  
      ✅ **Mobile-First Approach**  
      - Default styles for small screens (mobile)  
      - Use `@media (min-width: ...)` to add styles for larger screens  
      - **Ascending order of breakpoints** (small → large)  

      ```css
      /* Base styles (mobile) */
      @media (min-width: 768px) { ... }   /* Tablet */
      @media (min-width: 1024px) { ... }  /* Desktop */
      ```

      ✅ **Desktop-First Approach**  
      - Default styles for large screens (desktop)  
      - Use `@media (max-width: ...)` to override styles on smaller screens  
      - **Descending order of breakpoints** (large → small)  

      ```css
      /* Base styles (desktop) */
      @media (max-width: 1024px) { ... }  /* Tablet */
      @media (max-width: 768px) { ... }   /* Mobile */
      ```

  65. **Why Mobile-First is Preferred**  
      - Most users browse on mobile devices  
      - Loads fewer styles on smaller screens → better performance  
      - Easier to scale up than down  
      - Promotes **progressive enhancement**

  66. **Practical Example**  
      - Layout starts with vertical stacking.  
      - At `768px`, increase font size and center content.  
      - At `1024px`, switch to horizontal `flex` layout.  

      ```css
      .card {
        font-size: 16px;
      }

      @media (min-width: 768px) {
        .card {
          font-size: 18px;
        }
      }

      @media (min-width: 1024px) {
        .card {
          display: flex;
          font-size: 20px;
        }
      }
      ```

      ## First responsive project, on Day6 in 'index2.html' and 'styler.css' .From thsi project all the learnings I could get are listed from serial no, 67 to  72

  67. **Mobile First Grid-Based Layout – Key Concept**  
      - Mobile-first means default layout is built for small screens.
      - Using `min-width` media queries, the layout progressively scales up for larger screens.
      - This project uses grid and adjusts layout by:
          - Modifying `grid-template-columns` and `grid-template-rows`
          - Adjusting `width` and `height` of the container accordingly

  68. **Attributes That Directly Drive Responsiveness**  
      - The layout behavior is heavily influenced by these 5 core CSS properties:
          - `display` → `grid` creates a structured layout system.
          - `grid-template-columns` → controls number of columns.
          - `grid-template-rows` → controls number of rows.
          - `width` → defines horizontal space container takes.
          - `height` → defines vertical space container takes.
      - All breakpoints were tuned using only these, making the layout clean and easy to debug.

  69. **Width-Height ↔ Grid Structure Ratio Insight**  
      - There's a direct relationship between the **grid structure** and the **container size**.
      - Examples:
          - Mobile (1 col × 4 rows):  
            `width: 200px; height: 800px;` → ratio 1:4
          - Tablet (2 cols × 2 rows):  
            `width: 400px; height: 400px;` → ratio 1:1
          - Desktop (4 cols × 1 row):  
            `width: 800px; height: 200px;` → ratio 4:1
      - ✅ This intentional ratio matching ensures:
          - Evenly spaced boxes
          - No stretching
          - Visually balanced grid at all screen sizes

  70. **Why This Pattern Works So Well**  
      - Responsive grid feels smooth and clean because:
          - Grid cell count = width/height visual ratio
          - Layout symmetry is preserved on every screen
          - Grid boxes retain similar shape across breakpoints
      - 🔁 Changing only `grid-template` and matching dimensions is a minimal yet powerful technique.

  71. **Takeaway**  
      - If your `grid-template-columns` is increasing, your width should scale similarly.
      - If `grid-template-rows` reduces, your height can reduce too.
      - 📐 Think of it as visual math:

          ```text
          Columns : Rows ≈ Width : Height
          ```

      - This mindset makes responsive layout design much more predictable and scalable.

      - 💡 Summary:

      - The idea that width/height ≈ columns/rows is a logical design pattern, not a technical rule.
      - It works universally, but whether you follow it strictly depends on your design goal.

      - Let me know if you want a visual grid breakdown showing what happens when ratios don't match!

  72. **Why Not Used Flexbox in this project inspite it's capabilities using 'wrap' property?**
    
      - Flexbox is best for **1D layouts** (either row **or** column).
      - Our layout needs **2D control** → both rows **and** columns (like 2×2 **or** 4×1 grids).  
      - For full-page or complex responsive designs, combine both. Use Flexbox inside Grid items for optimal control.
      - Flexbox requires extra work (like wrapping, manual widths) to simulate what Grid does natively.
      - Grid simplifies things with:

          ```css
          grid-template-columns: repeat(2, 1fr);
          grid-template-rows: repeat(2, 1fr);
          ```

        which Flexbox can't do directly or cleanly.
      - ✅ Conclusion: **CSS Grid** is a better tool for this type of structured, multi-directional layout.

  73. **Box Shadow – Visual Depth & Effects**

      - `box-shadow` adds visual **depth, glow, or lighting** effects to an element.
      - Syntax: `box-shadow: offset-x offset-y blur-radius spread-radius color;`
      - Shadows can be applied on multiple sides simultaneously by **comma-separating** values.
      - In this project:

        ```css
        .box {
          box-shadow:
            -5px 0 5px 10px rgba(255, 255, 255, 0.3),  /* left */
            5px 0 5px 10px rgba(255, 255, 255, 0.3),  /* right */
            0 5px 5px 1px rgba(255, 255, 255, 0.3),   /* bottom */
            0 -5px 5px rgba(255, 255, 255, 0.3);      /* top */
        }
        ```

      - Each shadow:  
        → `offset-x` (`±` value) = side of shadow  
        → `blur-radius` = softness  
        → `spread-radius` = size  
        → `color` = visual impact
      - You can also use `box-shadow` for **lighting effects**, e.g., to simulate a glowing sun:

        ```css
        .sun {
          box-shadow: 0px 0px 20px 10px rgb(238, 146, 26);
        }
        ```

      - Or multiple shadows from all directions for a bright glow:

        ```css
        .sun {
          box-shadow:
            -10px 0px 200px rgb(238, 192, 26),
            10px 0px 200px rgb(238, 192, 26),
            0px 10px 200px rgb(238, 192, 26),
            0px -10px 200px rgb(238, 192, 26);
        }
        ```

      - ⚠️ Shadow doesn’t affect layout or box dimensions — **purely visual**.

  74. **Overflow – Controlling Content Spillage**

      - `overflow` defines what happens if content exceeds the box boundary.
      - In this `.box`, it is used to **handle large/overflowing content**.

        ```css
        overflow: scroll;
        ```

      - This makes scrollbars appear **only if needed**, preserving layout.
      - Alternative:
        - `overflow: hidden;` → Cuts off anything beyond the box → no scroll
      - Used here to **avoid text/content spilling out**, especially if fixed height is small.
      - This ensures UI remains **contained, controlled, and usable** on all screen sizes.

  ### Day 7 – CSS Animations 🎞️

  75. **CSS Animation Introduction**

  - Animations let elements transition between styles **smoothly over time**.
  - Unlike transitions (triggered by interaction), animations can **run automatically** or be looped.

  76. **Using `@keyframes`**

    - `@keyframes` defines the **stages of animation** (like start, middle, end).
    - You assign this animation to an element using `animation-name`.

    ```css
    @keyframes mymove {
    0%   { left: 0%; top: 0%; }
    25%  { left: 91.5%; top: 0%; background-color: lightgreen; }
    50%  { left: 91.5%; top: 90%; background-color: lightgoldenrodyellow; }
    70%  { left: 0%; top: 90%; background-color: lightsalmon; }
    100% { left: 0%; top: 0%; background-color: crimson; }
    }

  77. **Applying Animation to an Element**

  ```css
  .anim {
  width: 100px;
  height: 100px;
  background-color: coral;
  position: absolute;
  animation-name: mymove;
  animation-duration: 5s;
  animation-iteration-count: 5;
  animation-timing-function: linear;
  animation-delay: 2s;
  animation-direction: alternate;
  animation-fill-mode: forwards;
  }
    ```

  78. **📌 Explanation of each animation property:**

  | Property                 | Purpose                                                                                  |
  |--------------------------|------------------------------------------------------------------------------------------|
  | `animation-name`         | Refers to the `@keyframes` block to use                                                 |
  | `animation-duration`     | Total time to complete one cycle (e.g., 5s)                                            |
  | `animation-delay`        | Wait time before animation starts (e.g., 2s)                                           |
  | `animation-iteration-count` | Number of times the animation runs (e.g., 5, or infinite)                            |
  | `animation-direction`    | Direction of movement – normal, reverse, alternate, alternate-reverse                   |
  | `animation-fill-mode`    | What styles apply before and after animation                                            |
  | `animation-timing-function` | Controls animation speed curve (e.g., linear, ease, ease-in, ease-out)               |


  79. **Visual Description of the Animation**

  `The .anim box`:

  - Starts at top-left → moves to top-right → then bottom-right → bottom-left → back to top-left

  - Changes background color at each keyframe

  - Repeats the cycle 5 times with smooth motion

  - After completion, it remains at the final state (fill-mode: forwards)

  - Hovering over it changes background to lightcoral

  80. **Practical Tips**

      - Use `position`: absolute with defined left/top in `keyframes` to control movement

      - Use `animation-delay:` with `animation-fill-mode` to prepare pre-animation visual state

      - `alternate` ensures the element animates forward then backward, creating a looped bounce effect

  81. **🧪 Experiment Ideas:**

  - Replace `left` and `top` with `transform: translate(...)` for smoother GPU-     powered animations

  - Add `scale()` or `rotate()` transforms inside keyframes for rotation effects

  - Combine with opacity for fading in/out elements

### Day 8- CSS Transitions & Transforms 
  

  82. # 🎯 CSS `transform` Properties – Practical Reference

  This guide summarizes all key CSS transform properties with 2-line explanations and real-world notes. Useful for both beginners and frontend devs looking to polish UI/UX transitions.

  ---

  83. ## 🔹 Scale Properties

  ### `transform: scale(n)`
  - Scales the element **uniformly** in both width and height.
  - `scale(2)` doubles size; `scale(0.5)` halves it.

  ### `transform: scaleX(n)`
  - Scales the element **horizontally** (width only).
  - Example: `scaleX(2)` stretches the width x2.

  ### `transform: scaleY(n)`
  - Scales the element **vertically** (height only).
  - Example: `scaleY(1.5)` increases height by 50%.

  ### `transform: scaleZ(n)`
  - Applies scaling along the **Z-axis (depth)**.
  - Requires `perspective` on parent to be visible.

  ---

  84. ## 🔹 Translate Properties

  ### `transform: translate(x, y)`
  - Moves the element on both **X and Y axes**.
  - `translate(100px, 50px)` moves right and down.

  ### `transform: translateX(n)`
  - Moves the element **horizontally**.
  - `translateX(200px)` moves 200px to the right.

  ### `transform: translateY(n)`
  - Moves the element **vertically**.
  - `translateY(-50px)` moves up by 50px.

  ### `transform: translateZ(n)`
  - Moves the element **in or out** of the screen (3D).
  - Needs a parent with `perspective` to render properly.

  ---

  85. ## 🔹 Rotate Properties

  ### `transform: rotate(deg)` or `rotateZ(deg)`
  - Rotates the element in **2D space** (Z-axis).
  - `rotate(360deg)` spins it fully once.

  ### `transform: rotateX(deg)`
  - Rotates element around the **X-axis** (horizontal flip).
  - Creates a card-flip effect in 3D when used with `perspective`.

  ### `transform: rotateY(deg)`
  - Rotates element around the **Y-axis** (vertical flip).
  - Often used for rotating menu icons or 3D image galleries.

  ### `transform: rotateZ(deg)`
  - Same as `rotate()` — spins on the **Z-axis (flat plane)**.
  - `rotateZ(90deg)` rotates clockwise by 90 degrees.

  ---

  86. ## 🔹 Skew Properties

  ### `transform: skewX(deg)`
  - Skews element **horizontally**, slanting left or right.
  - Used in stylized titles, buttons, or hover effects.

  ### `transform: skewY(deg)`
  - Skews element **vertically**, slanting up or down.
  - Creates dynamic, tilted layouts or banners.

  ---

  87. ## 📝 Notes

  - These `transform` properties work best with `transition` for smooth effects.
  - You can combine multiple transforms like:
    ```css
    transform: scale(1.2) rotate(15deg) translateX(20px);

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

    ⚠️ Use !important sparingly. It breaks the natural cascade and can make debugging CSS difficult.
        ----
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




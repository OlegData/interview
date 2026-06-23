# CSS Interview Questions and Answers

## **1. What is CSS and what does it stand for?**

CSS stands for Cascading Style Sheets.
It is a stylesheet language used to describe the presentation and appearance of HTML documents. CSS controls how web page elements are displayed, including colors, fonts, spacing, layout, and responsiveness.

Key Benefits of CSS

- Separates content (HTML) from presentation (CSS)
- Makes websites easier to maintain
- Ensures consistent styling across multiple pages
- Supports responsive design for different devices
- Enables animations and visual effects

## **2. What are the different ways to include CSS in HTML?**

There are three main ways to include CSS in HTML:

- Inline CSS. CSS is written directly inside an HTML element using the style attribute.
- Internal (Embedded) CSS. CSS is placed inside a <style> tag in the <head> section of the HTML document.
- External CSS. CSS is stored in a separate .css file and linked to the HTML document.

## **3. What is CSS specificity and how is it calculated?**

CSS specificity is the set of rules browsers use to determine which CSS rule should be applied when multiple rules target the same element.
Specificity is often represented as:

- Inline styles
- Number of ID selectors
- Number of class selectors, attributes, and pseudo-classes
- Number of element selectors and pseudo-elements

## **4. What is the CSS cascade and inheritance?**

The CSS cascade is the process the browser uses to determine which CSS rule should be applied when multiple rules target the same element.

The cascade considers:

- Importance (!important)
- Specificity (IDs > Classes > Elements)
- Source order (later rules override earlier ones if specificity is equal)

Inheritance is the mechanism by which some CSS properties automatically pass from a parent element to its children.

Common Inherited Properties

- color
- font-family
- font-size
- font-weight
- line-height
- text-align
- visibility

## **5. What are CSS selectors and their types?**

CSS selectors are patterns used to select HTML elements that you want to style.

They tell the browser which elements a CSS rule should apply to.

1. Universal Selector (*) - Selects all elements.
2. Element (Type) Selector - Selects all elements of a specific type.
3. Class Selector (.class) - Selects elements with a specific class.
4. ID Selector (#id) - Selects a specific element with a unique ID.
5. Grouping Selector (,) - Applies the same styles to multiple selectors.
6. Descendant Selector (space) - Selects elements inside another element.
7. Child Selector (>) - Selects direct children only.
8. Adjacent Sibling Selector (+) - Selects the next sibling immediately following an element.
9. General Sibling Selector (~) - Selects all following sibling elements.
10. Attribute Selector ([attribute]) - Selects elements based on attributes.
11. Pseudo-Class Selector (:) - Selects elements in a special state.
12. Pseudo-Element Selector (::) - Selects a specific part of an element.

## **6. What is the difference between class and ID selectors?**

Both class and ID selectors are used to target HTML elements in CSS, but they serve different purposes.
A class selector (.class) can be used for multiple elements on a page, while an ID selector (#id) should be unique and used for only one element. Also, ID selectors have higher specificity than class selectors.

| Feature              | Class Selector                        | ID Selector                        |
| -------------------- | ------------------------------------- | ---------------------------------- |
| Syntax in CSS        | `.classname`                          | `#idname`                          |
| Syntax in HTML       | `class="box"`                         | `id="header"`                      |
| Reusable             | Yes, can be used on multiple elements | No, should be unique on the page   |
| Specificity          | Lower                                 | Higher                             |
| Multiple per element | An element can have multiple classes  | An element should have only one ID |
| Typical use          | Styling groups of elements            | Identifying a specific element     |

## **7. What are pseudo-classes and pseudo-elements?**

Pseudo-classes are used to define a special state of an element, such as when a user hovers over it or when it is the first child. Pseudo-elements are used to style specific parts of an element, such as the first letter or content before the element.

## **8. What is the universal selector (*)?**

The universal selector (*) selects all elements on a page. It is often used to apply global styles such as resetting margins and paddings.

## **9. What are attribute selectors?**

Attribute selectors are used to select HTML elements based on their attributes or attribute values. They are useful when you want to style elements according to specific attributes without adding extra classes or IDs.

## **10. What is the difference between margin and padding?**

Margin is the space outside an element's border, while padding is the space inside the border between the content and the border.
Padding increases the space inside the element, and margin increases the space between elements.
In short: margin = outside spacing, padding = inside spacing.

## **11. What is the CSS box model?**

The CSS box model describes how elements are structured and how their size is calculated. Every element consists of four parts: content, padding, border, and margin.

From inside to outside:

- Content - the actual text or image.
- Padding - space between the content and the border.
- Border - the border around the element.
- Margin - space outside the border.
In short, the box model consists of content, padding, border, and margin, and it determines the final size and spacing of an element.

## **12. What are CSS units (px, em, rem, %, vw, vh)?**

CSS units are used to define sizes, spacing, and dimensions of elements.

- px (pixels) – fixed unit.
- em – relative to the font size of the parent element.
- rem – relative to the root (html) font size.
- % – relative to the parent element.
- vw (viewport width) – relative to the browser window width.
- vh (viewport height) – relative to the browser window height.

## **13. What is the difference between absolute and relative units?**

Absolute units have fixed values and do not change based on other elements or screen size, while relative units depend on another value such as the parent element, root element, or viewport size.
Examples of absolute units:

- px
- cm
- mm
- in

Examples of relative units:

- em
- rem
- %
- vw
- vh

In short: absolute units are fixed, whereas relative units adapt based on another reference value.

## **14. What are CSS custom properties (CSS variables)?**

CSS custom properties, also known as CSS variables, are reusable values that can be defined once and used throughout a stylesheet. They make CSS easier to maintain and update.
In short: CSS variables allow you to store reusable values and access them using the var() function.

## **15. What is the difference between display: none and visibility: hidden?**

display: none removes the element from the page layout completely, while visibility: hidden hides the element but keeps its space reserved in the layout.
In short:

display: none → hides the element and removes it from the document flow.
visibility: hidden → hides the element but keeps its place in the layout.

## **16. What are CSS comments and how to write them?**

CSS comments are used to add notes or explanations in the code. They are ignored by the browser and do not affect the styling.
In short: CSS comments are written between /* and */ and are used to document or explain the code.

## **17. What is the !important declaration?**

!important is a declaration that gives a CSS rule higher priority than normal rules. It overrides the standard cascade and specificity rules.

## **18. What is CSS reset and normalize?**

CSS Reset and Normalize are techniques used to make styles consistent across different browsers.

CSS Reset removes most default browser styles by setting margins, paddings, and other properties to zero.

Normalize.css does not remove all styles. Instead, it preserves useful browser defaults and makes them consistent across browsers.

## **19. What are vendor prefixes?**

Vendor prefixes are prefixes added to CSS properties to support experimental or browser-specific features before they become part of the official CSS standard.

Common prefixes:

- -webkit- → Chrome, Safari
- -moz- → Firefox
- -ms- → Internet Explorer
- -o- → Opera

## **20. What is progressive enhancement in CSS?**

Progressive enhancement is a development approach where you start with basic functionality and styling that works in all browsers, then add advanced CSS features for modern browsers without breaking the experience for older ones.

## **21. What are the different position values in CSS?**

CSS provides five main position values: static, relative, absolute, fixed, and sticky.

They control how an element is positioned on the page.

- static – default position; the element follows the normal document flow.
- relative – positioned relative to its normal position.
- absolute – positioned relative to the nearest positioned ancestor.
- fixed – positioned relative to the viewport and stays in place when scrolling.
- sticky – behaves like relative until a scroll threshold is reached, then acts like fixed.

## **22. What is the difference between static, relative, absolute, and fixed positioning?**

The main difference is how the element is positioned and what it is positioned relative to.

- static – default positioning. The element follows the normal document flow. Properties like top, left, right, and bottom do not work.
- relative – the element remains in the normal flow, but can be moved relative to its original position using top, left, right, or bottom.
- absolute – the element is removed from the normal flow and positioned relative to the nearest parent that has a position other than static.
- fixed – the element is removed from the normal flow and positioned relative to the viewport. It stays in the same place even when the page is scrolled.

## **23. What is sticky positioning?**

position: sticky is a combination of relative and fixed positioning.
The element behaves like a relative element until it reaches a specified scroll position, then it becomes fixed within its container.
A common use case is sticky headers, navigation bars, or table headers.

## **24. What is the z-index property?**

The z-index property controls the stacking order of positioned elements on the z-axis. Elements with a higher z-index appear in front of elements with a lower z-index.
Important: z-index works on positioned elements (relative, absolute, fixed, sticky).

## **25. What are floats and how do they work?**

Floats are a CSS property used to position elements to the left or right of a container, allowing other content such as text to wrap around them.

Values:

- float: left
- float: right
- float: none (default)

One issue with floats is that parent containers may collapse because floated elements are removed from the normal document flow. This is often fixed using clear or a clearfix technique.

In short: Floats move elements to the left or right and allow surrounding content to wrap around them.

## **25. What is clearfix and why is it needed?**

Clearfix is a technique used to make a parent container properly contain its floated child elements. Without clearfix, the parent's height may collapse because floated elements are removed from the normal document flow.

```css
.clearfix::after {
    content: "";
    display: block;
    clear: both;
}
```

## **26. What is the difference between block, inline, and inline-block?**

The difference is how the elements behave in the layout.

- Block elements start on a new line and take up the full available width.
- Inline elements stay in the same line and only take up as much width as their content.
- Inline-block elements stay in the same line like inline elements, but allow width and height to be set like block elements.

## **27. What is CSS Flexbox?**

Flexbox (Flexible Box Layout) is a one-dimensional CSS layout model used to align and distribute items inside a container. It makes it easy to create responsive layouts and control spacing, alignment, and ordering of elements.

```css
.container {
    display: flex;
}
```

Common properties:

- justify-content – aligns items along the main axis.
- align-items – aligns items along the cross axis.
- flex-direction – defines the direction (row or column).
- gap – adds space between items.
- flex-wrap – allows items to wrap onto multiple lines.

## **28. What are the main properties of flex container?**

The main properties of a flex container are used to control the direction, alignment, wrapping, and spacing of flex items.

Main flex container properties:

- flex-direction – defines the main axis (row, column, row-reverse, column-reverse).
- justify-content – aligns items along the main axis.
- align-items – aligns items along the cross axis.
- align-content – aligns multiple rows of items when wrapping is enabled.
- flex-wrap – allows items to wrap onto multiple lines.
- gap – sets spacing between flex items.

## **29. What are the main properties of flex items?**

Flex item properties control how individual items behave inside a flex container.

The main properties are:

- flex-grow – defines how much an item can grow relative to other items.
- flex-shrink – defines how much an item can shrink if there isn't enough space.
- flex-basis – sets the initial size of an item before growing or shrinking.
- flex – shorthand for flex-grow, flex-shrink, and flex-basis.
- align-self – overrides the container's align-items value for a specific item.
- order – changes the visual order of items.

## **30. What is CSS Grid?**

CSS Grid is a two-dimensional layout system that allows you to create rows and columns and build complex page layouts more easily than with floats or Flexbox.

Key Grid properties:

- grid-template-columns – defines columns.
- grid-template-rows – defines rows.
- gap – spacing between grid items.
- grid-column – controls item column placement.
- grid-row – controls item row placement.

## **31. What is the difference between Flexbox and Grid?**

The main difference is that Flexbox is a one-dimensional layout system, while Grid is a two-dimensional layout system.

- Flexbox works with either a row or a column at a time.
- Grid works with rows and columns simultaneously.

Use Flexbox when:

- Aligning items in a single row or column.
- Building navigation menus.
- Centering content.
- Creating small UI components.

Use Grid when:

- Creating full-page layouts.
- Building complex row-and-column structures.
- Controlling both horizontal and vertical placement.

## **32. What are grid lines, tracks, and areas?**

In CSS Grid, grid lines, tracks, and areas are the fundamental building blocks of a grid layout.

- Grid lines are the horizontal and vertical lines that divide the grid.
- Grid tracks are the spaces between two grid lines (rows or columns).
- Grid areas are rectangular sections made up of one or more grid cells.

## **33. What is the fr unit in CSS Grid?**

The fr (fraction) unit is a CSS Grid unit that represents a fraction of the available space in the grid container. It allows columns and rows to share the remaining space proportionally.

The available space is divided into 4 parts:

- First column → 1 part (25%)
- Second column → 2 parts (50%)
- Third column → 1 part (25%)

The fr unit is preferred over percentages because it automatically distributes the remaining available space and makes responsive layouts easier to create.

## **34. What are CSS media queries?**

Media queries are a CSS feature used to apply different styles based on the device's screen size, resolution, or other characteristics. They are the foundation of responsive web design.

Use cases:

- Mobile-friendly layouts
- Responsive navigation menus
- Adjusting font sizes and spacing
- Showing or hiding elements on different devices

## **35. What is mobile-first vs desktop-first approach?**

Mobile-first and desktop-first are two approaches to responsive web design.

Mobile-first means you write styles for mobile devices first, then use min-width media queries to enhance the layout for larger screens.

```css
.container {
    width: 100%;
}

@media (min-width: 768px) {
    .container {
        width: 750px;
    }
}
```

Desktop-first means you write styles for desktop screens first, then use max-width media queries to adapt the layout for smaller screens.
```css
.container {
    width: 1200px;
}

@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

Mobile-first is generally preferred because most users access websites from mobile devices, and it encourages simpler, more performant designs.

## **35. What are breakpoints in responsive design?**

Breakpoints are specific screen widths at which the layout or styling of a website changes to provide a better user experience on different devices. They are usually implemented using media queries.

Common breakpoints:

- 576px → mobile
- 768px → tablet
- 992px → small desktop
- 1200px → large desktop

Important: Modern responsive design focuses on content-based breakpoints rather than targeting specific devices.

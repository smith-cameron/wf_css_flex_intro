# Flex
When using the display properties block, inline and inline-block responsiveness becomes a much more labor intensive task and there are more up-to-date/intuitive ways to achieve a more  responsive layout.
## WHY?
1. **Flexible Layout**: Flexbox allows you to **create flexible and dynamic layouts** that **adapt** to different screen sizes and device orientations. You can easily control the size and alignment of elements within a flex container, making it easier to create **responsive designs**.
2. **Easy Alignment**: Flexbox **simplifies the process of aligning elements both horizontally and vertically within a container**.  
    - **align items along the main axis (horizontal)**
    - **cross axis (vertical) using properties like `justify-content` and `align-items`.**
3. **Spacing and Distribution**:  You can **evenly distribute items**, align them to the 
    - start
    - end
    - center

of the container, or **space them out with adjustable gaps**.

4. **Automatic Wrapping**: Flexbox automatically wraps flex items onto new lines when they exceed the width of the container.
5. **Cross-browser Compatibility**: Flexbox is well-supported across modern web browsers, making it a reliable and widely adopted layout solution.

## Syntax
1. `display: flex;`: This property establishes a flex container. 
2. It enables the use of other flex properties on the container and its children.

**DEFAULTS**
- `flex-direction: row;`
- `justify-content: flex-start;`
- `align-items: stretch ;`

**HTML**
```html
<div id="display_flex">
	<button type="submit">Click me</button>
	<button type="submit">Also Click me</button>
	<p class="red_border">First P</p>
	<a class="red_border" href="#">Im a link</a>
	<p class="red_border">Second p</p>
	<img src="./images/cats/godotocat.png" alt="godotocat" class="flexed_item">
</div>
```

**CSS**
```css
#display_flex{
    border: thin solid;
    display: flex;
}
.flexed_items{
    /* Styles for flex items */
    border: thin solid red;
}
```
### flex-direction
`flex-direction`: Determines the **main axis of the flex container** and the **direction** in which flex items are laid out. Possible values are:

- row (default): left to right 
- row-reverse: right to left 
- column: top to bottom
- column-reverse: bottom to top

**CSS**
```css
#display_flex{
    border: thin solid;
    display: flex;
    /* flex-direction: row; */
    flex-direction: row-reverse;
    /* flex-direction: column; */
    /* flex-direction: column-reverse; */
```
### justify-content
`justify-content`: Defines how flex items are aligned along the main axis of the flex container. It distributes space between and around content items. <br>
Possible values are:
- `flex-start`: Items are **packed toward the start** of the flex container(**default**).
- `flex-end`: Items are **packed toward the end** of the flex container.
- `center`: Items are **centered along the main axis** of the flex container.
- `space-between`: Items are **evenly distributed along the main axis**. 
    - first item is at the start
    - last item is at the end.
- `space-around`: Items are evenly distributed along the main axis with **equal space around them**.
- `space-evenly`: Items are distributed so that there is an **equal amount of space around each item**

**CSS**
```css
.display_flex{
    flex-direction: row;
    /* ----- justify-content -----*/
    /* justify-content: flex-start; */
    /* justify-content: flex-end; */
    /* justify-content: center; */
    /* justify-content: space-between; */
    /* justify-content: space-around; */
    justify-content: space-evenly;
}
```

### align-items
`align-items`: Defines how flex items are **aligned along the cross axis** of the flex container. It **aligns flex items when they do not take up all available space** on the cross-axis. Possible values are:
- `stretch`: Items are **stretched to fill the container** (**default**).
- `flex-start`: Items are aligned **to the start** of the cross axis.
- `flex-end`: Items are aligned **to the end** of the cross axis.
- `center`: Items are **centered** along the cross axis.
- `baseline`: Items are aligned such as their **baselines align**.

**CSS**
```css
.display_flex{
    margin: 20px 0;
    border: thick solid;
    /* ---------- */
    display: flex;
    justify-content: center;
    
    /* ----- align-items -----*/
    /* align-items: stretch ; */
    /* align-items: flex-start ; */
    /* align-items: flex-end ; */
    align-items: baseline ;
    /* align-items: center ; */
}
```
### flex-wrap
By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.
- `nowrap` (**default**): all flex items will be on one line
- `wrap`: flex items will **wrap onto multiple lines, from top to bottom**.
- `wrap-reverse`: flex items will **wrap onto multiple lines from bottom to top**.

**CSS**
```css
.display_flex{
    margin: 20px 0;
    border: thick solid;
    /* ---------- */
    display: flex;
    justify-content: space-evenly;
    align-items: center ;

    /* ----- flex-wrap -----*/
    /* flex-wrap: nowrap ; */
    flex-wrap: wrap ;
    /* flex-wrap: wrap-reverse; */
}
```
### gap
Explicitly controls the space between flex items. Again... it applies that spacing _only between items_ not on the outer edges.

**CSS**
```css
.display_flex{
    margin: 20px 0;
    border: thick solid;
    /* width: 300px; */
    /* ---------- */
    display: flex;
    flex-wrap: wrap ;

    /* ----- gap -----*/
    gap: 20px;
    /* row-gap: 10px; */
    /* column-gap: 20px; */
    /* row-gap column gap  */
    /* gap: 10px 20px;  */
}
```
## Position
Starter code:

**HTML**
```html
<div id="postition_demo">
	<img src="" alt="" class="position_example">
</div>
```
**CSS**
```css
#postition_demo{
    border: solid thick;
}
```
### Position: relative;
- The `position: relative;` property positions an element relative to its normal position
- When an element is positioned relatively, it still occupies space in the document flow, but its final position can be adjusted using the `top`, `right`, `bottom`, and `left` properties.

**CSS**
```css
.position_example{
    border: red solid thin;
    position: relative;
    top: 20px;
    left: 20px;
    width: 150px;
}
```
### Position: absolute;
- The `position: absolute;` property positions an element relative to its nearest positioned ancestor (usually the viewport or the browser window).
- When an element is positioned absolutely, it is taken out of the normal document flow, meaning it doesn't affect the positioning of other elements.
- Absolute positioning is often used to precisely position elements within a container or the entire webpage.

**CSS**
```css
.position_example{
    border: red solid thin;
    position: absolute;
    top: 20px;
    left: 20px;
    width: 150px;
}
```

### Position: fixed;
- The `position: fixed;` property positions an element relative to the browser window or viewport, regardless of scrolling.
- When an element is positioned fixed, it is taken out of the document flow.
- Fixed positioning is often used for elements like navigation bars or advertisements that should remain visible regardless of scrolling.

**CSS**
```css
.position_example{
    border: red solid thin;
    position: fixed;
    top: 20px;
    left: 20px;
    width: 150px;
}
```

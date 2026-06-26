CSS transitions allows you to change  property values smoothly, over a given duration.
To create a transition effect, you must specify the CSS property you want to add a transition to, and the duration of the transition.
+ **transition-property** (required)
+ **transition-duration** (required)
+ **transition-timing-function**
+ **transition-delay**
The following example shows a 100px * 100px `<div>` element. The `<div>` element has specified a transition effect for the width property, with a duration of 2 seconds:
```css
div{
	width:100px;
	height:100px;
	background-color:red;
	transition:width 2s;
}
```
**How to trigger the transition:**
The transition is triggered when there is a change in the element's properties. This often happens within pseudo-classes (:hover, :active, :focus, or :checked).
So, from the code above, the transition effect will start when the width property changes value.
Now, we add a `div:hover` class that specifies a new value for the width property when a user mouses over the `<div>` element:
```css
div:hover{
	width:300px;
}
```
Notice that when the cursor mouses out of the element, it will gradually change back to its original style.

##### CSS transition speed curve
The `transition-timing-function` property specifies the speed curve of the transition effect.
This property can have one of the following values:
- `ease` - transition will start slow, then go fast, and end slow (this is default)
- `linear` - transition will keep the same speed from start to end
- `ease-in` - transition will start slow
- `ease-out` - transition will end slow
- `ease-in-out` - transition will have a slow start and end
- `cubic-bezier(n,n,n,n)` - lets you define your own values in a cubic-bezier function
```css
#div1 {transition-timing-function: linear;}  
#div2 {transition-timing-function: ease;}  
#div3 {transition-timing-function: ease-in;}  
#div4 {transition-timing-function: ease-out;}  
#div5 {transition-timing-function: ease-in-out;}
```

##### CSS transition delay
The `transition-delay` property specifies a delay before the transition starts.
The `transition-delay` value is defined in seconds (s) or milliseconds (ms).
The following example has a 1 second delay before starting:
```css
div{
	transition-delay:1s;
}
```

##### More examples
```css
div{
	transition-property: width;  
	transition-duration: 2s;  
	transition-timing-function: linear;  
	transition-delay: 1s;
}
```

```css
.container{
    background-color: blue;
    width: 100px;
    height: 100px;
    color:white;
    transition-property: width,height;
    transition-duration: 1s;
    transition-timing-function: ease-out;
    /* transition-timing-function: ease-in; */
    /* transition-timing-function: ease-in-out; */
    transition-delay: 0s;
}

.container:hover{
    background-color: red;
    width:200px;
	height:200px;
}
```
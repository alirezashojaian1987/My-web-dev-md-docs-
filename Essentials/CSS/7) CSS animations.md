CSS allows animation of HTML elements without using JavaScript!

**CSS animation-name and animation-duration**
The `animation-name` property specifies a name for the animation.
The `animation-duration` property defines how long an animation should take to complete. If this property is not specified, no animation will occur, because the default value is 0s (0 seconds).

**CSS @keyframes Rule**
When you specify CSS styles inside the `@keyframes` rule, the animation will gradually change from the current style to the new style at certain times.
To get an animation to work, you must bind the animation to an element.
```css
.container{
	background-color:aquamarine;
	color:black;
	width:200px;
	height:200px;
	animation-name:anim1;
	animation-duration:5s;
}

@keyframes anim1{
	from{
		background-color:red;
	}
	
	to{
		background-color:yellow;
	}
}
```
*Note:* It is also possible to use percent. By using percent, you can add as many style changes as you like.
```css
.container{
	background-color:aquamarine;
	color:black;
	width:200px;
	height:200px;
	animation-name:anim1;
	animation-duration:5s;
}

@keyframes anim1{
	0%{
		background-color:red;
	}
	
	25%{
		background-color:blue;
	}
	
	50%{
		background-color:purple;
	}
	
	75%{
		background-color:orange;
	}
	
	100%{
		background-color:lime;
	}
}
```
The % is percentage of the animation-duration attribute.

**CSS animation-delay**
The `animation-delay` property specifies a delay for the start of an animation.
```css
animation-delay:2s;
```

**CSS animation-iteration-count property**
The `animation-iteration-count` property specifies the number of times an animation should run.
```css
.container{
	background-color:aquamarine;
	color:black;
	width:200px;
	height:200px;
	animation-name:anim1;
	animation-iteration-count:infinite;
	/*animation-iteration-count:3;*/
	animation-duration:5s;
}
```

**CSS animation-direction property**
The `animation-direction` property specifies whether an animation should be played forwards, backwards or in alternate cycles.

The animation-direction property can have the following values:
- `normal` - The animation is played as normal (forwards). This is default
- `reverse` - The animation is played in reverse direction (backwards)
- `alternate` - The animation is played forwards first, then backwards
- `alternate-reverse` - The animation is played backwards first, then forwards
```css
.container{
	background-color:aquamarine;
	color:black;
	width:200px;
	height:200px;
	animation-name:anim1;
	animation-iteration-count:infinite;
	animation-duration:5s;
	animation-direction:alternate;
}
```

**CSS animation-timing-function**
It's like transition.
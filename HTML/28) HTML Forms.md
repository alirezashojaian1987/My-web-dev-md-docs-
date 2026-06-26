#### Forms
An HTML form is used to collect user input. The user input is most often sent to a server for processing.
```html
<!DOCTYPE html>
<html>
<body>

<h2>HTML Forms</h2>

<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form> 

<p>If you click the "Submit" button, the form-data will be sent to a page called "/action_page.php".</p>

</body>
</html>
```

##### The `<input>` element
The HTML `<input>` element is the most used form element.
An `<input>` element can be displayed in many ways, depending on the `type` attribute.

| Type                      | Description                                                      |
| ------------------------- | ---------------------------------------------------------------- |
| `<input type="text">`     | Displays a single-line text input field                          |
| `<input type="radio">`    | Displays a radio button (for selecting one of many choices)      |
| `<input type="checkbox">` | Displays a checkbox (for selecting zero or more of many choices) |
| `<input type="submit">`   | Displays a submit button (for submitting the form)               |
| `<input type="button">`   | Displays a clickable button                                      |
**Text fields:**
The `<input type="text">` defines a single-line input field for text input.
```html
<form>  
  <label for="fname">First name:</label><br>  
  <input type="text" id="fname" name="fname"><br>  
  <label for="lname">Last name:</label><br>  
  <input type="text" id="lname" name="lname">  
</form>
```
###### All input types
- `<input type="button">`
- `<input type="checkbox">`
- `<input type="color">`
- `<input type="date">`
- `<input type="datetime-local">`
- `<input type="email">`
- `<input type="file">`
- `<input type="hidden">`
- `<input type="image">`
- `<input type="month">`
- `<input type="number">`
- `<input type="password">`
- `<input type="radio">`
- `<input type="range">`
- `<input type="reset">`
- `<input type="search">`
- `<input type="submit">`
- `<input type="tel">`
- `<input type="text">`
- `<input type="time">`
- `<input type="url">`
- `<input type="week">`
[ see the examples here ](https://www.w3schools.com/html/html_form_input_types.asp)
[ Input attributes](https://www.w3schools.com/html/html_form_attributes.asp)

##### The `<label>` element
Notice the use of the `<label>` element in the example above.
The `<label>` tag defines a label for many form elements.
The `<label>` element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focuses on the input element.
The `<label>` element also helps users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the `<label>` element, it toggles the radio button/checkbox.
The `for` attribute of the `<label>` tag should be equal to the `id` attribute of the `<input>` element to bind them together.

##### Radio buttons
The `<input type="radio">` defines a radio button.
Radio buttons let a user select ONE of a limited number of choices.
```html
<p>Choose your favorite Web language:</p>  
  
<form>  
  <input type="radio" id="html" name="fav_language" value="HTML"> 
  <label for="html">HTML</label><br>  
  <input type="radio" id="css" name="fav_language" value="CSS">  
  <label for="css">CSS</label><br>  
  <input type="radio" id="javascript" name="fav_language" value="JavaScript">  
  <label for="javascript">JavaScript</label>  
</form>
```

##### Checkboxes
The `<input type="checkbox">` defines a **checkbox**.
Checkboxes let a user select ZERO or MORE options of a limited number of choices.
```html
<form>  
  <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">  
  <label for="vehicle1"> I have a bike</label><br>  
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car">  
  <label for="vehicle2"> I have a car</label><br>  
  <input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">  
  <label for="vehicle3"> I have a boat</label>  
</form>
```

##### The submit button
The `<input type="submit">` defines a button for submitting the form data to a form-handler.
The form-handler is typically a file on the server with a script for processing input data.
The form-handler is specified in the form's `action` attribute.
```html
<form action="/action_page.php">  
  <label for="fname">First name:</label><br>  
  <input type="text" id="fname" name="fname" value="John"><br>  
  <label for="lname">Last name:</label><br>  
  <input type="text" id="lname" name="lname" value="Doe"><br><br> 
  <input type="submit" value="Submit">  
</form>
```

##### The name attribute for `<input>`
Notice that each input field must have a `name` attribute to be submitted.
If the `name` attribute is omitted, the value of the input field will not be sent at all.
```html
<form action="/action_page.php">  
  <label for="fname">First name:</label><br>  
  <input type="text" id="fname" value="John"><br><br>  
  <input type="submit" value="Submit">  
</form>
```

#### Form attributes
##### The action attribute
The `action` attribute defines the action to be performed when the form is submitted.
Usually, the form data is sent to a file on the server when the user clicks on the submit button.
In the example below, the form data is sent to a file called "action_page.php". This file contains a server-side script that handles the form data:
```html
<form action="/action_page.php">  
  <label for="fname">First name:</label><br>  
  <input type="text" id="fname" name="fname" value="John"><br>  
  <label for="lname">Last name:</label><br>  
  <input type="text" id="lname" name="lname" value="Doe"><br><br>  
  <input type="submit" value="Submit">  
</form>
```
*!Note:* If the `action` attribute is omitted, the action is set to the current page.
*Note:* You can also use the target attribute alongside action.

##### The method attribute
The `method` attribute specifies the HTTP method to be used when submitting the form data.
The form-data can be sent as URL variables (with `method="get"`) or as HTTP post transaction (with `method="post"`).
The default HTTP method when submitting form data is GET.
```html
<form action="/action_page.php" method="get">
```

```html
<form action="/action_page.php" method="post">
```

*Notes on GET:*
- Appends the form data to the URL, in name/value pairs
- NEVER use GET to send sensitive data! (the submitted form data is visible in the URL!)
- The length of a URL is limited (2048 characters)
- Useful for form submissions where a user wants to bookmark the result
- GET is good for non-secure data, like query strings in Google
*Notes on POST:*
- Appends the form data inside the body of the HTTP request (the submitted form data is not shown in the URL)
- POST has no size limitations, and can be used to send large amounts of data.
- Form submissions with POST cannot be bookmarked

##### The autocomplete attribute
The `autocomplete` attribute specifies whether a form should have autocomplete on or off.
When autocomplete is on, the browser automatically complete values based on values that the user has entered before.
```html
<form action="/action_page.php" autocomplete="on">
```

##### The Novalidate attribute
The `novalidate` attribute is a boolean attribute.
When present, it specifies that the form-data (input) should not be validated when submitted.
```html
<form action="/action_page.php" novalidate>
```

#### Form other elements
##### The `<select>` element:
The `<select>` element defines a drop-down list:
```html
<label for="cars">Choose a car:</label>  
<select id="cars" name="cars">  
  <option value="volvo">Volvo</option>  
  <option value="saab">Saab</option>  
  <option value="fiat">Fiat</option>  
  <option value="audi">Audi</option>  
</select>
```
The `<option>` element defines an option that can be selected.
By default, the first item in the drop-down list is selected.
To define a pre-selected option, add the `selected` attribute to the option:
```html
<option value="fiat" selected>Fiat</option>
```

Use the `size` attribute to specify the number of visible values:
```html
<label for="cars">Choose a car:</label>  
<select id="cars" name="cars" size="3">  
  <option value="volvo">Volvo</option>  
  <option value="saab">Saab</option>  
  <option value="fiat">Fiat</option>  
  <option value="audi">Audi</option>  
</select>
```

##### The `<textarea>` element
The `<textarea>` element defines a multi-line input field (a text area):
```html
<textarea name="message" rows="10" cols="30">  
The cat was playing in the garden.  
</textarea>
```
The `rows` attribute specifies the visible number of lines in a text area.
The `cols` attribute specifies the visible width of a text area.
*Note:* you can also style the sizes.

##### The `<button>` element
The `<button>` element defines a clickable button:
```html
<button type="button" onclick="alert('Hello World!')">Click Me!</button>
```

##### The `<fieldset>` and `<legend>` elements
The `<fieldset>` element is used to group related data in a form.
The `<legend>` element defines a caption for the `<fieldset>` element.
```html
<form action="/action_page.php">  
  <fieldset>  
    <legend>Personalia:</legend>  
    <label for="fname">First name:</label><br>  
    <input type="text" id="fname" name="fname" value="John"><br>  
    <label for="lname">Last name:</label><br>  
    <input type="text" id="lname" name="lname" value="Doe"><br><br>  
    <input type="submit" value="Submit">  
  </fieldset>  
</form>
```

##### The `<datalist>` element
The `<datalist>` element specifies a list of pre-defined options for an `<input>` element.
Users will see a drop-down list of the pre-defined options as they input data.
The `list` attribute of the `<input>` element, must refer to the `id` attribute of the `<datalist>` element.
```html
<form action="/action_page.php">  
  <input list="browsers">  
  <datalist id="browsers">  
    <option value="Edge">  
    <option value="Firefox">  
    <option value="Chrome">  
    <option value="Opera">  
    <option value="Safari">  
  </datalist>  
</form>
```

##### The `<output>` element
The `<output>` element represents the result of a calculation (like one performed by a script).
```html
<form action="/action_page.php"  
  oninput="x.value=parseInt(a.value)+parseInt(b.value)">  
  0  
  <input type="range"  id="a" name="a" value="50">  
  100 +  
  <input type="number" id="b" name="b" value="50">  
  =  
  <output name="x" for="a b"></output>  
  <br><br>  
  <input type="submit">  
</form>
```


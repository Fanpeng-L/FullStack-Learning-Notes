[check html standard here](https://html.spec.whatwg.org/multipage/named-characters.html)

# 1. HTML elements

<img alt="html elements" src="../images/Front-end/html element.png" width="500"/>

<img alt="h1" src="../images/Front-end/h1.png" width="500">

# 2. Inline & Block elements

<img width="600" alt="inline block elements" src="../images/Front-end/inline block elements.png">

<img width="600" alt="div and span" src="../images/Front-end/div and span.png">

# 3. HTML entities

Some reserved character  
`&...;`

# 4. Semantic HTML elements

<img width="500" alt="Semantic elements" src="../images/Front-end/semantic elements.png"><br>

this kind of tags are more meaningful, more friendly for screenreader and other codes.

📍emmet shortcuts

# 5. table

<img width="393" alt="Screenshot 2023-10-07 at 15 43 06" src="../images/Front-end/table.png">

preview on web:

<img width="490" alt="table preview" src="../images/Front-end/table-preview.png">

# 6. Form

## action:

<img width="600" alt="form action" src="../images/Front-end/form-action.png">

## input:

- difference types
- placeholder

## label:

use the `for=""` to connect the input `id=""`

<img width="600" alt="label for" src="../images/Front-end/label-for.png">

<img width="391" alt="label for preview" src="../images/Front-end/label-for-preview.png">

## button:

if we put the button inside of the form, the defualt function is to `Submit`.

## `name` attribute:

<img width="600" alt="name" src="../images/Front-end/name.png">

when submit:

<img width="400" alt="name submit preview" src="../images/Front-end/name preview.png">

## checkbox:

```html
<form action="/birds">
  <input type="checkbox" name="agree_tos" id="agree" />
  <label for="agree">I agree to everything.</label>
  <button>Submit</button>
</form>
```

<img width="286" alt="checkbox" src="../images/Front-end/checkbox.png">

## radio:

to specify which one radio choice, we need `value` attribute in the input:

<img width="700" alt="value attribute" src="../images/Front-end/value attribute.png">

## select & option:

<img width="700" alt="select option" src="../images/Front-end/select-option.png">

## range:

```html
<form action="">
  <label for="volume">Change the volume</label>
  <input type="range" id="volume" min="1" max="10" name="volume" />
  <button>Submit</button>
</form>
```

<img width="441" alt="range" src="../images/Front-end/range.png">

## textarea

## validation

- Required
- minlength
- maxlength

```html
<form action="">
  <label for="firstname">Enter firstname:</label>
  <input type="text" id="firstname" name="firstname" required />
  <button>Submit</button>
</form>
```

<img width="400" alt="validation" src="../images/Front-end/validation.png">

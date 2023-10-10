# 💜 CSS Basics:

## 1. Rules

<img width="642" alt="CSS rule" src="../images/Front-end/css-rule.png">

- **Inline Style** (not good idea)
- **style element** (not good idea)
- **style.css external stylesheet** ✅

## 2. Color system

- RGB
- hexadecimal

## 3. Absolute & Relative units

<img width="545" alt="relative absolute" src="../images/Front-end/relative-absolute.png">

Absolute units is not recommended used for responsive websites.

## 4. CSS Selectors

- universal
- element
- , (select several elements at the same time)
- \# (ID selector)
- . (class selector)
- space descendent selector
- \+ (adjecent)
- \> (direct child)
- input[type="password"] attribute selector
- : pseudo class -- states (checked, active, hover...)
- :: pseudo elements --- specific parts of an element

## 5. Cascade & Specificity

The order in styles matters.

When multiple rules apply to the same element, the more specific selector "wins".

<img width="600" alt="specific" src="../images/Front-end/specific.png">

## 6. Inheritance

some elements are inheritable, some are not.

## 7. Box model

### border

- border-width
- border-color
- border-style

<img width="313" alt="border" src="../images/Front-end/border.png">

looks like 👇

<img width="321" alt="border preview" src="../images/Front-end/border-preview.png">

### margin & padding

<img width="601" alt="margin and padding" src="../images/Front-end/margin-padding.png">

> `body` has default margin, so we can set to 0 when we start to style the CSS.

## 8. Display property

- display: inline
- display: block
- display: inline-block

change the take up space.

<img width="801" alt="display property" src="../images/Front-end/display.png">

## 9. Relative Units

### percentage

<img width="400" alt="Screenshot 2023-10-08 at 00 26 13" src="../images/Front-end/percentage.png">

### em

<img width="400" alt="em" src="../images/Front-end/em.png">

> one problem em can cause:
> <img width="230" alt="em problem" src="../images/Front-end/em-problem.png">

### rem

<img width="482" alt="Screenshot 2023-10-08 at 00 36 45" src="../images/Front-end/rem.png">

<br>

# 💜 CSS Properties

## 1. alpha channel & opacity

<img width="350" alt="Screenshot 2023-10-08 at 16 46 10" src="../images/Front-end/opacity-alpha-channel.png">

## 2. position

- static
- relative
- absolute (depend on the parent position property)
- fixed
- sticky

## 3. transition

- transition-propert
- transition-duration
- transition-timing-function
- transition-delay

## 4. transform - also applies to its children

- rotate()
- scale()
- translate()
- skew()

> a tip on calculations function:
> <img width="197" alt="calculation function" src="../images/Front-end/calc().png">

<br>

# 💜 responsive

## 1. flexbox

- flex-direction

<img width="400" alt="flex direction row" src="../images/Front-end/flex-direction-row.png">

<img width="400" alt="flex direction column" src="../images/Front-end/flex-direction-column.png">

- justify-content (main axis)
- flex-wrap
- align-items (cross axis)
- align-content (only has effect on flex-wrap)
- align-self
- flex-basis
- flex-grow
- flex-shrink

👇

flex: 1 1 600px // grow, shrink, basis

## 2.responsive: media queries

@media min-width:

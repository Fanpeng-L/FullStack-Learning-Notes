# 1. CSS Basics:
## Rule
<img width="642" alt="Screenshot 2023-10-07 at 18 13 46" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/d3e64732-0839-41ae-837d-e60840c2fcf5">

**1. Inline Style** not good idea  
**2. <style> element**  
**3. style.css external stylesheet**✅  

## color system:  
- RGB  
- hexadecimal  

## Absolute & Relative units  
<img width="545" alt="Screenshot 2023-10-07 at 19 34 21" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/ae479fa4-07cc-4d89-99c3-b38c23480652">  

Absolute units is not recommended used for responsive websites.

## (1) CSS Selectors
- universal
- element
- ,  (select several elements at the same time)
- \# (ID selector)
- .  (class selector)
- space descendent selector
- \+ (adjecent)
- \> (direct child)
- input[type="password"]  attribute selector
- : pseudo class -- states (checked, active, hover...)
- :: pseudo elements --- specific parts of an element

## (2) cascade & specificity
The order in styles matters.  
when multiple rules apply to the same element, the more specific selector "wins".   
<img width="622" alt="Screenshot 2023-10-07 at 23 35 43" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/33573f3f-d511-4dae-a521-5c2b51213a50">

## (3) inheritance
some elements are inheritable, some not.

## (4) box model  
### border
border-width; border-color; border-style  
<img width="313" alt="Screenshot 2023-10-07 at 23 47 20" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/58825360-5dcb-49e3-9641-b1ae02c6a8ce"> looks like👉:
<img width="321" alt="Screenshot 2023-10-07 at 23 48 18" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/4b8acf9f-af75-476b-8799-7ca837b30051">

<img width="601" alt="Screenshot 2023-10-08 at 00 08 09" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/184b28a1-bd59-4647-bde3-311b914cdfb7">

💡`body` has defaulf margin, so we can set to 0 when we start to style the CSS.

### display property
- display: inline  
- display: block  
change the take up space.  
<img width="801" alt="Screenshot 2023-10-08 at 00 18 45" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/0768af25-81e8-4209-8973-5b6d249807a3">

## (5) Relative Units
### percentage:  
<img width="499" alt="Screenshot 2023-10-08 at 00 26 13" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/f32f6a71-b3bb-4912-9128-2cdf617e869b">

### em
<img width="481" alt="Screenshot 2023-10-08 at 00 31 25" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/c80902d4-fbc3-4b34-a2ee-10bed7b6513a">

one problem em can cause is:  
<img width="230" alt="Screenshot 2023-10-08 at 00 38 06" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/6c4b4d5f-d7d8-4cce-8d0f-1088c1cd3550">

### rem
<img width="482" alt="Screenshot 2023-10-08 at 00 36 45" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/ea5df885-35b2-4046-8970-6f5b64628623">

Absolute and Relative:
<img width="618" alt="Screenshot 2023-10-03 at 16 55 15" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/17af5454-213e-4868-a1cc-502e0acd1fbc">


# 2. CSS Properties

## opacity & alpha channel
<img width="350" alt="Screenshot 2023-10-08 at 16 46 10" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/83677a25-1b8f-4eed-b7ba-c7a5dcd066f8">

## position
- static
- relative
- absolute (depend on the parent position property)
- fixed
- sticky

## transition
it includes: transition-property, transition-duration, transition-timing-function, and transition-delay.

## transform - also applies to its children
- rotate()
- scale()
- translate()
- skew()  

<img width="197" alt="Screenshot 2023-10-08 at 18 56 57" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/31a39431-8b41-4a12-b50f-37ccac1238ef">

# 3. responsive & flexbox




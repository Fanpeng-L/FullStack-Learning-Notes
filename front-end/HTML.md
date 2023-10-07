[html standard](https://html.spec.whatwg.org/multipage/named-characters.html)

### 1. HTML elements
<img src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/d307c1cf-239f-4256-961e-0b28439eaac3" alt="drawing" width="800"/>

![Untitled design (1)](https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/7972f1ce-9c6f-4674-a02b-aac068b54158)

### 2. Inline & Block elements  
<img width="657" alt="Screenshot 2023-10-07 at 00 10 17" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/4b564aae-3549-4a43-993d-b795e7f0cf76">
<img width="610" alt="Screenshot 2023-10-07 at 00 14 41" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/51a95fb0-1c79-428d-a080-d5091666cb90">


### 3. HTML entities  
Some reserved character  
&...;   


### 4. Writing semantic HTML elements  
<img width="511" alt="Screenshot 2023-10-07 at 00 33 51" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/710f8b3a-78bd-4fe0-b321-2644b60e30c1"><br>
this kind of tags are more meaningful, more friendly for screenreader and other codes.  

📍emmet shortcuts

### 5. table  
<img width="393" alt="Screenshot 2023-10-07 at 15 43 06" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/9bec0d44-baf3-46a5-bcab-b89d84148ef8">

preview on web:  
<img width="490" alt="Screenshot 2023-10-07 at 15 42 27" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/d125fe71-93d9-40bc-87a2-f981a7da98c7">


### 6. Form  
#### action:  
<img width="615" alt="Screenshot 2023-10-07 at 16 15 29" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/3fd8708a-d427-4d2b-ac8c-d13ff27b90bf">  

#### input:  
- difference types
- placeholder

#### label:  
use the `for=""` to connect the input `id=""`  
<img width="775" alt="Screenshot 2023-10-07 at 16 33 30" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/284303a5-7765-4b13-806c-ade9823ed787">
<img width="391" alt="Screenshot 2023-10-07 at 16 34 21" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/bc575b0c-a5a5-497a-bf01-cb7f11059718">

#### button:  
if we put the button inside of the form, the defualt function is to `Submit`.

#### the `name` attribute:    
<img width="876" alt="Screenshot 2023-10-07 at 16 45 52" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/1f4cbf16-9246-44be-b32b-69d1ddfa9ebf">

<img width="482" alt="Screenshot 2023-10-07 at 16 43 49" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/8a1e32b0-2b54-4bf9-a90a-0faaa57dcb82">

#### checkbox:  
```html
    <form action="/birds">
      <input type="checkbox" name="agree_tos" id="agree" />
      <label for="agree">I agree to everything.</label>
      <button>Submit</button>
    </form>
```   
<img width="286" alt="Screenshot 2023-10-07 at 17 08 16" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/dec1dd4b-efe5-4c7d-b987-ce9114005146">

#### radio:
to specify which radio choice, we need `value` attribute in the input:  
<img width="660" alt="Screenshot 2023-10-07 at 17 15 52" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/54703829-a3e1-4ca0-afcb-bdd2e23bb180">

#### select & option:  
<img width="790" alt="Screenshot 2023-10-07 at 17 17 41" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/ea930ff4-c28a-4160-a826-9bc557c54091">


#### range:  
```html
    <form action="">
      <label for="volume">Change the volume</label>
      <input type="range" id="volume" min="1" max="10" name="volume" />
      <button>Submit</button>
    </form>
```   
<img width="441" alt="Screenshot 2023-10-07 at 17 26 45" src="https://github.com/Fanpeng-L/FullStack-Learning-Notes/assets/90544605/3fbb820c-ed7a-44f0-8d67-155a22f0f938">   

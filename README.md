## Pink Flower SVG Mask Effect

![ezgif com-gif-maker (5)](https://user-images.githubusercontent.com/94214512/187004872-85a845a2-e887-4a8a-b352-462dc4ccf956.gif)<br>
This project was to practice using SVG's mask effect.

### Goal of the project

1. practice SVG's mask effect
2. practice JavaScript 'Mousemove' event

### Languages

HTML, CSS, JavaScript, and SVG

### Features

1. SVG mask effect

```html
<!-- mask glass -->
<mask id="mask-glass">
  <circle cx="60.56" cy="60.56" r="47.75" style="fill:white" />
</mask>

<g mask="url(#mask-glass)">
  <rect class="bg-gray" x="0" y="0" width="100%" height="100%"></rect>
  <rect class="bg" x="0" y="0" width="100%" height="100%"></rect>
</g>
```

2. mousemove event

```js
 <script>
    window.addEventListener('DOMContentLoaded', ()=>{
      const magnifierEl = document.querySelector('.magnifier');
      const maskglassEl = document.querySelector('#mask-glass circle')


         window.addEventListener('mousemove', (event)=>{
            const x1 = event.clientX;
            const y1 = event.clientY;

             const magnifierRect = magnifierEl.getBoundingClientRect()
             const magnifierRectWidth = magnifierRect.width
             const magnifierRectHeight = magnifierRect.height

             const maskglassRect = maskglassEl.getBoundingClientRect()
             const maskglassHalfWidth = maskglassRect.width/2
             const maskglassHalfHeight = maskglassRect.height/2

             magnifierEl.style.transform = `translate(${x1 - magnifierRectWidth - maskglassHalfWidth - 0.5}px,${y1 - magnifierRectHeight - maskglassHalfHeight + 23}px)`
             maskglassEl.style.transform = `translate(${x1 - maskglassHalfWidth}px, ${y1 - maskglassHalfHeight}px)`
       })
    })
</script>
```

### self-reflection

The mask effect has given me a lot of creative ideas for the future.
For example, I would like to make a mini-game 'find a four leaf clover' in the future.
Also, I want to learn more about why '.magnifier' and '#mask-glass circle' are seperately moved instead of combined together? I'm curious because I had to transform each element according to their size in JavaScript.

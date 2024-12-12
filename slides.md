---
theme: seriph
title: Intro To Fullstack | Abhinav
info: |
  ## Intro To Fullstack | Abhinav
  Prepared for AKCSSC 2024 - GECK December 14, 2024
class: text-center
drawings:
  persist: false
mdc: true
---

# Intro to Fullstack

<div>
  For AKCSSC'25
</div>

<!--
Oi! <br>
This presentation is made using Slidev.
<br>
 [Slidev Site](https://sli.dev/)
 <br>
 [My github](https://github.com/ruralad) (nothing here)
-->

---

# About Me
<br>
<v-clicks>
  <p>Product Dev @ Envestnet</p>
  <p>Java</p>
  <p>Fullstack Javascript (mainly) & others</p>
</v-clicks>


<!--
https://www.envestnet.com/
-->

---
transition: slide-up
level: 2
---

# What To Expect
<br>
  <p class="m-0 p-0" v-click>Fundamentals of Fullstack Web</p>
  <span class="inline-block">
    <p v-click v-mark.orange.underline="4">Writing responsible code</p>
    <p v-click class="inline-block" v-mark.orange.underline="4">Getting Industry Ready</p>
  </span>



<!--
- You need to know what you are writing
- You need to know others will work on the same code
- Example - Error Handling
- Responsible code and industry ready is closely related
-->

---

# How to Follow Along

<br>
<v-clicks>
  <p>Slides + Code</p>
  <p>Ask Questions Anytime</p>
  <p>Notes?</p>
</v-clicks>

---
transition: slide-up
layout: statement
---

# The Journey of a Web Request

<br>

<v-clicks>
<p >
<img class="inline"  src="https://fonts.gstatic.com/s/e/notoemoji/latest/261d_fe0f/512.gif" alt="☝" width="32" height="32">
 User initiates action</p>
<p><img class="inline" src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f6eb/512.gif" alt="🛫" width="32" height="32">
 Request travels through network</p>
<p><img class="inline" src="https://fonts.gstatic.com/s/e/notoemoji/latest/2699_fe0f/512.gif" alt="⚙" width="32" height="32"> Servers process the request</p>

<p><img class="inline" src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f6ec/512.gif" alt="🛬" width="32" height="32"> Data transforms and travels</p>
<p><img class="inline"  src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f440/512.gif" alt="👀" width="32" height="32"> User sees the result</p>
</v-clicks>

---

<img src="/request-1.png" />

<!--

## Authentication
<br>
Take an example of a banking app. 
<br>

- User can type their mail(or mobile or any unique data point), and get their current account details, bank balance and all
- Cant anybody get details of everyone by brute force?

## Authorization
- If one person knows the email of the other person, even if the person is
authenticated, where is the logic to identify if the current user is actually asking only for their data
-->

---

<img src="/request-2.png" />

<!--
## Consider URL Shortner

- Same request is made by thousands of users. 
- request -> server fires a request to check database for the shortened url -> database returns the complete url

## Other examples
- Election, new data is came in every 5 minutes
- Banking app itself, where we show like currency exchange rate( same for all users)

-->

---

<img src="/request-3.png" />

<!--
## Why cache ?
- Faster data retrieval : cache stored in memory, significantly faster than accessing data from a hard disk, better UX
- Reduced database load, improving Scalability

## What happens when our app go viral ?
- URL Shortner goes viral. Our server is overloaded
- First, we can improve our server resources (increase cpu and ram)
- But what happens when its practically impossible? : We can introduce more servers
- Scaling is implemented. We have done VERTICAL and HORIZONTAL scaling
- How to choose which request to pass to which server? : LOAD BALANCER

-->

---

<img src="/request-4.png" />

<!--
Scaling is extremely important in the modern web as it allows websites and applications to handle increasing user traffic and data loads without experiencing performance issues or service disruptions

- We can scale db and cache, auth services as well and bring them closer to the user
- An Indian user dont have to request american db's for data, we can introduce a new server in Mumbai to provide better UX

-->

---
# Table of contents

You can use the `Toc` component to generate a table of contents for your slides:

```html
<Toc minDepth="1" maxDepth="1" />
```

The title will be inferred from your slide content, or you can override it with `title` and `level` in your frontmatter.

::right::

<Toc text-sm minDepth="1" maxDepth="2" />

---

layout: image-right
image: https://cover.sli.dev

---

# Code

Use code snippets and get the highlighting directly, and even types hover!

```ts {all|5|7|7-8|10|all} twoslash
// TwoSlash enables TypeScript hover information
// and errors in markdown code blocks
// More at https://shiki.style/packages/twoslash

import { computed, ref } from "vue";

const count = ref(0);
const doubled = computed(() => count.value * 2);

doubled.value = 2;
```

<arrow v-click="[4, 5]" x1="350" y1="310" x2="195" y2="334" color="#953" width="2" arrowSize="1" />

<!-- This allow you to embed external code blocks -->

<<< @/snippets/external.ts#snippet

<!-- Footer -->

[Learn more](https://sli.dev/features/line-highlighting)

<!-- Inline style -->
<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

<!--
Notes can also sync with clicks

[click] This will be highlighted after the first click

[click] Highlighted with `count = ref(0)`

[click:3] Last click (skip two clicks)
-->

---

## level: 2

# Shiki Magic Move

Powered by [shiki-magic-move](https://shiki-magic-move.netlify.app/), Slidev supports animations across multiple code snippets.

Add multiple code blocks and wrap them with <code>````md magic-move</code> (four backticks) to enable the magic move. For example:

````md magic-move {lines: true}
```ts {*|2|*}
// step 1
const author = reactive({
  name: "John Doe",
  books: [
    "Vue 2 - Advanced Guide",
    "Vue 3 - Basic Guide",
    "Vue 4 - The Mystery",
  ],
});
```

```ts {*|1-2|3-4|3-4,8}
// step 2
export default {
  data() {
    return {
      author: {
        name: "John Doe",
        books: [
          "Vue 2 - Advanced Guide",
          "Vue 3 - Basic Guide",
          "Vue 4 - The Mystery",
        ],
      },
    };
  },
};
```

```ts
// step 3
export default {
  data: () => ({
    author: {
      name: "John Doe",
      books: [
        "Vue 2 - Advanced Guide",
        "Vue 3 - Basic Guide",
        "Vue 4 - The Mystery",
      ],
    },
  }),
};
```

Non-code blocks are ignored.

```vue
<!-- step 4 -->
<script setup>
const author = {
  name: "John Doe",
  books: [
    "Vue 2 - Advanced Guide",
    "Vue 3 - Basic Guide",
    "Vue 4 - The Mystery",
  ],
};
</script>
```
````

---

# Components

<div grid="~ cols-2 gap-4">
<div>

You can use Vue components directly inside your slides.

We have provided a few built-in components like `<Tweet/>` and `<Youtube/>` that you can use directly. And adding your custom components is also super easy.

```html
<Counter :count="10" />
```

<!-- ./components/Counter.vue -->
<Counter :count="10" m="t-4" />

Check out [the guides](https://sli.dev/builtin/components.html) for more.

</div>
<div>

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.65" />

</div>
</div>

<!--
Presenter note with **bold**, *italic*, and ~~striked~~ text.

Also, HTML elements are valid:
<div class="flex w-full">
  <span style="flex-grow: 1;">Left content</span>
  <span>Right content</span>
</div>
-->

---

## class: px-20

# Themes

Slidev comes with powerful theming support. Themes can provide styles, layouts, components, or even configurations for tools. Switching between themes by just **one edit** in your frontmatter:

<div grid="~ cols-2 gap-2" m="t-2">

```yaml
---
theme: default
---
```

```yaml
---
theme: seriph
---
```

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-default/01.png?raw=true" alt="">

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-seriph/01.png?raw=true" alt="">

</div>

Read more about [How to use a theme](https://sli.dev/guide/theme-addon#use-theme) and
check out the [Awesome Themes Gallery](https://sli.dev/resources/theme-gallery).

---

# Clicks Animations

You can add `v-click` to elements to add a click animation.

<div v-click>

This shows up when you click the slide:

```html
<div v-click>This shows up when you click the slide.</div>
```

</div>

<br>

<v-click>

The <span v-mark.red="3"><code>v-mark</code> directive</span>
also allows you to add
<span v-mark.circle.orange="4">inline marks</span>
, powered by [Rough Notation](https://roughnotation.com/):

```html
<span v-mark.underline.orange>inline markers</span>
```

</v-click>

<div mt-20 v-click>

[Learn more](https://sli.dev/guide/animations#click-animation)

</div>

---

# Motions

Motion animations are powered by [@vueuse/motion](https://motion.vueuse.org/), triggered by `v-motion` directive.

```html
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :click-3="{ x: 80 }"
  :leave="{ x: 1000 }"
>
  Slidev
</div>
```

<div class="w-60 relative">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.5, rotate: -50 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-square.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ y: 500, x: -100, scale: 2 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-circle.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-triangle.png"
      alt=""
    />
  </div>

  <div
    class="text-5xl absolute top-14 left-40 text-[#2B90B6] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Slidev
  </div>
</div>

<!-- vue script setup scripts can be directly used in markdown, and will only affects current page -->
<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

<div
  v-motion
  :initial="{ x:35, y: 30, opacity: 0}"
  :enter="{ y: 0, opacity: 1, transition: { delay: 3500 } }">

[Learn more](https://sli.dev/guide/animations.html#motion)

</div>

---

# LaTeX

LaTeX is supported out-of-box. Powered by [KaTeX](https://katex.org/).

<div h-3 />

Inline $\sqrt{3x-1}+(1+x)^2$

Block

$$
{1|3|all}
\begin{aligned}
\nabla \cdot \vec{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \vec{B} &= 0 \\
\nabla \times \vec{E} &= -\frac{\partial\vec{B}}{\partial t} \\
\nabla \times \vec{B} &= \mu_0\vec{J} + \mu_0\varepsilon_0\frac{\partial\vec{E}}{\partial t}
\end{aligned}
$$

[Learn more](https://sli.dev/features/latex)

---

# Diagrams

You can create diagrams / graphs from textual descriptions, directly in your Markdown.

<div class="grid grid-cols-4 gap-5 pt-4 -mb-6">

```mermaid {scale: 0.5, alt: 'A simple sequence diagram'}
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

```mermaid {theme: 'neutral', scale: 0.8}
graph TD
B[Text] --> C{Decision}
C -->|One| D[Result 1]
C -->|Two| E[Result 2]
```

```mermaid
mindmap
  root((mindmap))
    Origins
      Long history
      ::icon(fa fa-book)
      Popularisation
        British popular psychology author Tony Buzan
    Research
      On effectiveness<br/>and features
      On Automatic creation
        Uses
            Creative techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid
```

```plantuml {scale: 0.7}
@startuml

package "Some Group" {
  HTTP - [First Component]
  [Another Component]
}

node "Other Groups" {
  FTP - [Second Component]
  [First Component] --> FTP
}

cloud {
  [Example 1]
}

database "MySql" {
  folder "This is my folder" {
    [Folder 3]
  }
  frame "Foo" {
    [Frame 4]
  }
}

[Another Component] --> [Example 1]
[Example 1] --> [Folder 3]
[Folder 3] --> [Frame 4]

@enduml
```

</div>

Learn more: [Mermaid Diagrams](https://sli.dev/features/mermaid) and [PlantUML Diagrams](https://sli.dev/features/plantuml)

---

foo: bar
dragPos:
square: 691,32,167,\_,-16

---
dragPos:
  square: -119,-22,0,0
---

# Draggable Elements

Double-click on the draggable elements to edit their positions.

<br>

###### Directive Usage

```md
<img v-drag="'square'" src="https://sli.dev/logo.png">
```

<br>

###### Component Usage

```md
<v-drag text-3xl>
  <div class="i-carbon:arrow-up" />
  Use the `v-drag` component to have a draggable container!
</v-drag>
```

<v-drag pos="663,206,261,_,-15">
  <div text-center text-3xl border border-main rounded>
    Double-click me!
  </div>
</v-drag>

<img v-drag="'square'" src="https://sli.dev/logo.png">

###### Draggable Arrow

```md
<v-drag-arrow two-way />
```

<v-drag-arrow pos="67,452,253,46" two-way op70 />

---

src: ./pages/imported-slides.md
hide: false

---


---

# Monaco Editor

Slidev provides built-in Monaco Editor support.

Add `{monaco}` to the code block to turn it into an editor:

```ts {monaco}
import { ref } from "vue";
import { emptyArray } from "./external";

const arr = ref(emptyArray(10));
```

Use `{monaco-run}` to create an editor that can execute the code directly in the slide:

```ts {monaco-run}
import { version } from "vue";
import { emptyArray, sayHello } from "./external";

sayHello();
console.log(`vue ${version}`);
console.log(
  emptyArray<number>(10).reduce(
    (fib) => [...fib, fib.at(-1)! + fib.at(-2)!],
    [1, 1]
  )
);
```

---

layout: center
class: text-center

---

# Learn More

[Documentation](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/resources/showcases)

<PoweredBySlidev mt-10 />

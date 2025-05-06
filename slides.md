---
theme: apple-basic
layout: statement
colorSchema: light
highlighter: shiki
drawings:
  persist: false
---

# Modernizing Austria's<br>Tax Services with <span class="accent">Next.js Microfrontends</span>

---
layout: statement
---

<h1>Opinions Are My Own!</h1>

---
layout: image
image: "/images/sad.png"
---

---
layout: intro
---

<div class="leading-8">
  <span class="font-extrabold">Markus Oberlehner</span><br>
  <span style="font-size:0.5em;">Software Engineer @ Austrian Federal Computing Centre</span>
</div>

<div class="leading-17 mt-10">
  Bluesky: <a href="https://bsky.app/profile/markus.oberlehner.net">@markus.oberlehner.net</a><br>
  Book: <a href="https://goodvuetests.com">goodvuetests.com</a>
</div>

---
layout: statement
---

<h1>Make It <span class="accent">Fit!</span></h1>

---
layout: intro
---

<ol>
  <li>Architecture / Organization</li>
  <li v-click>Technology / Team</li>
  <li v-click>Solutions / Architecture</li>
</ol>

---
layout: statement
---

<h1>Make Your <span class="accent">Architecture</span><br>Fit Your <span class="accent">Organization</span></h1>

---
layout: intro
---

<div class="leading-12 italic">
Organizations which design systems are constrained to produce designs which are copies of the communication structures of<br>these organizations.
</div>

<div class="text-sm mt-12">
— Melvin E. Conway, How Do Committees Invent?
</div>

---
layout: statement
---

<img src="/images/org-1.png" width="580"/>

---
layout: statement
---

<img src="/images/org-2.png" width="580"/>

---
layout: intro
---

<ul>
  <li>Choose an architecture that fits your organization</li>
  <li v-click>Be realistic! Don't let idealism guide your decisions</li>
</ul>

---
layout: statement
---

<h1>Make Your <span class="accent">Technology</span><br>Fit Your <span class="accent">Team(s)</span></h1>

---
layout: statement
---

<h1>Three<br><span class="accent">Evil Words</span></h1>

---
layout: statement
---

<h1>Microservices</h1>

---
layout: statement
---

<div class="flex flex-col items-center justify-center gap-4">
  <iframe src='https://app.sli.do/event/4L9FPRjTf2NPeSTKXEhkDb/embed/polls/ed9275c9-fb2f-4079-8739-75e4917460d0' width='400' height='260'></iframe>
  <img src="/images/poll-qr-microservices.png">
</div>

---
layout: statement
---

<h1><span class="accent">Single-page</span><br>Application</h1>

---
layout: statement
---

<div class="flex flex-col items-center justify-center gap-4">
  <iframe src='https://app.sli.do/event/4L9FPRjTf2NPeSTKXEhkDb/embed/polls/51160702-78c3-407a-af8c-02304b07991b' width='400' height='260'></iframe>
  <img src="/images/poll-qr-spa.png">
</div>

---
layout: statement
---

<h1><span class="accent">Full-stack</span><br>Developer</h1>

---
layout: statement
---

<div class="flex flex-col items-center justify-center gap-4">
  <iframe src='https://app.sli.do/event/4L9FPRjTf2NPeSTKXEhkDb/embed/polls/4d7a87c8-8008-44f0-bdf5-4a1d0ceadc02' width='400' height='260'></iframe>
  <img src="/images/poll-qr-fullstack.png">
</div>

---
layout: intro
---

<ul>
  <li><span class="font-extrabold">Microservices:</span> Backend Specialization</li>
  <li v-click><span class="font-extrabold">SPA:</span> Frontend Specialization</li>
  <li v-click><span class="font-extrabold">Full-stack Developer:</span> <span class="text-red-500">Generalization</span></li>
</ul>

---
layout: statement
---

<img src="/images/tech-1.png" width="280"/>

---
layout: statement
---

<img src="/images/tech-2.png" width="740"/>

---
layout: statement
---

<img src="/images/tech-3.png" width="740"/>

---
layout: statement
---

<img src="/images/tech-4.png" width="740"/>

---
layout: intro
---

<ul>
  <li>You need deep backend expertise for microservices!</li>
  <li v-click>You need deep frontend expertise for SPAs!</li> 
</ul>

---
layout: statement
---

<h1>Make Your <span class="accent">Solutions</span><br>Fit Your <span class="accent">Architecture</span></h1>

---
layout: statement
---

<img src="/images/solution-1.png" width="260"/>

---
layout: statement
---

<img src="/images/solution-2.png" width="460"/>

---
layout: statement
---

<img src="/images/solution-3.png" width="460"/>

---
layout: statement
---

<img src="/images/solution-4.png" width="360"/>

---
layout: statement
---

<img src="/images/solution-5.png" width="460"/>

---
layout: statement
---

<h1>Don't Let <span class="accent">Domain Teams</span><br>Build Generic Solutions!</h1>

---
layout: intro
---

<ul>
  <li><span class="font-extrabold">Platform teams:</span> build generic solutions</li>
  <li v-click><span class="font-extrabold">Domain teams:</span> build solutions tailored to their domain</li>
</ul>

---
layout: statement
---

<h1>Integrating a Next.js <span class="accent">Microfrontend</span> into a<br><span class="accent">Legacy Monolith</span></h1>

---
layout: statement
---

<img src="/images/module-federation.png" width="580"/>

---
layout: statement
---

<img src="/images/impl-1.png" width="1200"/>

---
layout: statement
---

<img src="/images/impl-2.png" width="580"/>

---
layout: statement
---

<img src="/images/impl-3.png" width="580" style="margin-top:-20px;"/>

---
layout: statement
---

<img src="/images/impl-4.png" width="800" style="margin-top:-20px;"/>

---
layout: intro
---

```html
<iframe
  id="my-microfrontend"
  src="https://my-app.com/mf/my-microfrontend"
  style="width:100%;height:100%;"
></iframe>
```

---
layout: intro
---

```ts {all|2|5-11|all}
const syncDimensions = ({ element, targetOrigin }) => {
  const resizeObserver = new ResizeObserver((entries) => {
    for (const entry of entries) {
      const contentBoxSize = entry.contentBoxSize[0];
      emit({
        name: "resize",
        data: {
          width: contentBoxSize?.inlineSize || 0,
          height: contentBoxSize?.blockSize || 0,
        },
      }, targetOrigin);
    }
  });
  resizeObserver.observe(element);
};
```

---
layout: intro
---

```ts {all|1|3|5-10|11-15|all}
import { customListener, mount } from "@fon/mf-sdk";

const myMicrofrontend = mount(document.querySelector("#my-microfrontend"));

// Add event listeners:
myMicrofrontend.addEventListener(
  customListener("submit-success", ({ data }) => {
    // ...
  }),
);
myMicrofrontend.addEventListener(
  customListener("submit-error", ({ message }) => {
    // ...
  }),
);
```

---
layout: statement
---

<img src="/images/impl-5.png" width="780"/>

---
layout: statement
---

<h1>Make Your <span class="accent">Architecture</span><br>Fit Your <span class="accent">Organization</span></h1>

---
layout: statement
---

<h1>Make Your <span class="accent">Technology</span><br>Fit Your <span class="accent">Team(s)</span></h1>

---
layout: statement
---

<h1>Make Your <span class="accent">Solutions</span><br>Fit Your <span class="accent">Architecture</span></h1>

---
layout: statement
---

<h1>Make It <span class="accent">Fit!</span></h1>

---
layout: intro
---

<div class="leading-8">
  <span class="font-extrabold">Markus Oberlehner</span><br>
  <span style="font-size:0.5em;">Software Engineer @ Austrian Federal Computing Centre</span>
</div>

<img src="/images/qr.png" style="width:280px;position:absolute;top:36px;right:36px;">

<div class="leading-17 mt-10">
  Bluesky: <a href="https://bsky.app/profile/markus.oberlehner.net">@markus.oberlehner.net</a><br>
  Book: <a href="https://goodvuetests.com">goodvuetests.com</a><br><br>
  <small><a href="https://github.com/maoberlehner/talk-microfrontend-modernization">github.com/maoberlehner/talk-microfrontend-modernization</a></small>
</div>

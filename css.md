1. – CSS Grid aur Flexbox mein difference kya hai? Kab kaunsa use karna chahiye?

Answer:

CSS Grid 2D layout ke liye hota hai – rows aur columns dono manage karta hai.

Flexbox 1D layout ke liye hota hai – ya to row direction ya column direction mein items arrange karta hai.

Agar aapko poore page ka layout design karna hai jaise header, sidebar, footer – Grid use karo.

Agar aapko buttons ya form elements ko line mein align karna hai – Flexbox use karo.

 2. – position: relative, absolute, fixed, sticky mein kya farak hai?

Answer:

relative: element apni normal position se offset hota hai lekin space wahi rakhta hai.

absolute: element nearest positioned ancestor ke relative position mein hota hai, aur document flow se bahar nikal jata hai.

fixed: viewport ke relative fixed hota hai – scroll hone par bhi wahi rahta hai.

sticky: scroll ke hisaab se behave karta hai. Jab scroll threshold cross hota hai tab fixed jaisa behave karta hai, warna normal flow mein hota hai.

3. – z-index kaise kaam karta hai?

Answer:

z-index define karta hai kaunsa element kisi dusre ke upar dikhega.

Higher z-index wale element upar dikhte hain.

Lekin z-index tabhi kaam karega jab element position property (relative, absolute, fixed, sticky) mein ho.

4. – Div ko center horizontally aur vertically kaise karoge?

Answer:
Method 1 – Flexbox:

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}


Method 2 – Grid:

.container {
  display: grid;
  place-items: center;
  height: 100vh;
}


Method 3 – Position:

.child {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

5. – CSS Box Model kya hai?
    Answer:
Box model mein 4 layers hoti hain:

Content – actual content jaise text ya image.

Padding – content aur border ke beech ka space.

Border – content ko surround karne wala border.

Margin – element aur dusre elements ke beech ka space.
Example:
Agar padding 20px, border 2px, margin 10px diya hai, to final size calculate karte waqt sab add hoga.

6. – :nth-child() aur :nth-of-type() mein kya difference hai?
Answer:

:nth-child() position ke hisaab se select karta hai, chahe type kuch bhi ho.

:nth-of-type() sirf usi type ke elements mein count karta hai.

Example:
Agar <div>, <p>, <div>, <p> hai – to p:nth-child(2) select karega dusra element jo p hai, lekin p:nth-of-type(1) select karega pehla p.

7. – CSS Transition aur Animation mein difference kya hai?
Answer:

Transition ek state se dusre state mein smooth change karne ke liye hai (jaise hover par color badalna).

Animation multiple steps mein complex movement ya effect create karta hai (jaise bouncing ball).

Transition example:
.button:hover {
  transition: background-color 0.3s ease;
  background-color: red;
}

Animation example:
@keyframes move {
  0% { left: 0; }
  100% { left: 100px; }
}
.box {
  animation: move 2s infinite alternate;
}

8. – Easing functions kya hote hain? ease-in, ease-out ka kya matlab hai?
Answer:
Easing define karta hai animation ka speed pattern.

ease-in: animation dheere start hota hai aur fast hota hai.

ease-out: fast start, dheere end hota hai.

linear: same speed throughout animation.

cubic-bezier: custom speed curve define karne ke liye.

9. – CSS Variables kya hain aur kaise use karte hain?
Answer:
CSS variables ya custom properties ko -- prefix se define karte hain.

:root {
  --primary-color: #3498db;
}
.button {
  background-color: var(--primary-color);
}

Benefits:
✔ Reusability
✔ Easy theming
✔ Maintainability
✔ Runtime updates possible

10. – Media queries kaise kaam karti hain? Example do.
Answer:
Media queries screen size ya device characteristics ke hisaab se CSS apply karte hain.
Example:

@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}

Yeh code screen 768px se chhoti hone par layout ko column mein badal dega.

11. – box-sizing: border-box kyun important hai?
Answer:
Agar default box model use karoge to width + padding + border = total width badh jayega.
border-box use karne par width ke andar padding aur border include ho jata hai, jisse layout predictable aur maintainable hota hai.

Example:

* {
  box-sizing: border-box;
}

12. – Accessibility ke liye CSS kaise madad karta hai?
Answer:
✔ Contrast achha rakhna
✔ Focus styles visible rakhna
✔ Animations ko disable karna agar user prefers-reduced-motion use kare
✔ Font size aur spacing readable rakhna
✔ Keyboard navigation ke liye outlines visible rakhna

Example:
button:focus {
  outline: 2px solid #000;
}

13. – CSS mein fallback kaise define karte hain?
Answer:
Agar variable undefined ho to fallback value use karo:

color: var(--text-color, black);

Yahan agar --text-color defined nahi hai to black apply hoga.

14. – Lazy loading kaise karte hain?
Answer:
Images ko slow loading se bachane ke liye loading="lazy" use karte hain.

<img src="image.jpg" loading="lazy" alt="example">

Isse page load fast hota hai aur resources tab load hote hain jab user scroll karta hai.

15. – CSS shorthand properties ka use kaise performance improve karta hai?
Answer:
Shortcuts likhne se code concise hota hai aur unnecessary repetition kam hoti hai.
Example:

margin: 10px 20px 30px 40px;
is equal to

margin-top: 10px;
margin-right: 20px;
margin-bottom: 30px;
margin-left: 40px;

Browser ke liye parsing easier hota hai.

16. How does CSS Grid’s grid-template-areas kaam karta hai? Example do.

Answer:
grid-template-areas layout ko visually naam dekar define karta hai.

.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-gap: 10px;
}
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.footer { grid-area: footer; }


Isse layout easily samajh mein aata hai aur code readable hota hai.

17. What’s the difference between auto-fill and auto-fit in grid layout?

Answer:

auto-fill: jitni jagah hai utni columns fill karta hai chahe woh khali ho ya nahi.

auto-fit: available space ke hisaab se columns adjust karta hai aur extra space collapse karta hai.

Example:

grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));

18. Explain how Flexbox’s flex-grow, flex-shrink, aur flex-basis kaam karte hain.

Answer:

flex-grow: space available hone par element kitna expand hoga.

flex-shrink: space kam hone par element kitna shrink karega.

flex-basis: default width ya height define karta hai jo available space ke alawa hota hai.

19. How to align one item differently than others in Flexbox?

Answer:
align-self property use karte hain:

.item-special {
  align-self: flex-end;
}


Isse sirf ek item alag position par align hota hai.

20. What is the difference between min-height and height in layout control?

Answer:

height: element ki exact height define karta hai.

min-height: minimum allowed height hoti hai, agar content zyada hai to automatically expand karega.

✅ Animations & Effects Questions
21. How to create a CSS-only parallax scroll effect?

Answer:
Background image ko background-attachment: fixed; ke saath use karte hain:

.section {
  background-image: url('parallax.jpg');
  background-attachment: fixed;
  background-size: cover;
}


Isse scroll karne par background slow move karta hai.

22. How do you prevent layout shift during animations?

Answer:
✔ Animations ko transform aur opacity par apply karo, kyunki ye GPU accelerated hote hain.
❌ width, height, margin, padding par animation karne se reflow hota hai.

8. How can you animate a gradient background in CSS?

Answer:
@keyframes ke saath gradient ke colors ko animate karte hain:

@keyframes gradient {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
.background {
  background: linear-gradient(45deg, red, blue, green);
  background-size: 300% 300%;
  animation: gradient 5s infinite alternate;
}

✅ Selectors & Specificity Questions
23. Explain how CSS cascade works when multiple rules apply.

Answer:

Inline styles sabse zyada priority lete hain.

IDs class ya tag selectors se zyada strong hote hain.

Specificity score calculate hota hai – jitne zyada identifiers, utni high priority.

Agar specificity same hai to last wala rule apply hoga.

24. How to override styles from third-party libraries without using !important?

Answer:
✔ Higher specificity use karo (jaise div.header .button)
✔ Inline styles avoid karo
✔ Custom class attach karke control lo
✔ CSS variables se styling override karo

✅ Performance Optimization Questions
25. Why avoid using too many nested selectors?

Answer:
✔ Deep nesting se browser ko zyada calculation karni padti hai → slow rendering.
✔ Code maintain karna mushkil ho jata hai.
✔ Specificity conflict ka risk badhta hai.

26. Explain how critical CSS improves website performance.

Answer:
✔ Critical CSS sirf above-the-fold content ke liye use hota hai → page jaldi dikhne lagta hai.
✔ Baaki CSS ko defer ya async load karke page speed badhayi ja sakti hai.

27. How do you reduce reflow aur repaint issues in CSS?

Answer:
✔ Transform aur opacity par animations karo
✔ Avoid heavy layout changes
✔ Minimize use of expensive properties jaise box-shadow ya filters
✔ Use will-change hint jab zarurat ho

✅ Accessibility Related Questions
28. How to ensure focus is visible for keyboard users?

Answer:

:focus {
  outline: 3px solid #00f;
}


✔ Keyboard navigation mein elements easily visible hote hain
✔ Accessibility guidelines fulfill hoti hain

29. How to use prefers-reduced-motion to improve user experience?

Answer:

@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}


✔ Jo users motion se uncomfortable hain unke liye animations disable kar dete hain.

✅ Real-World Scenarios
30. How to style a dark mode using CSS variables?

Answer:

:root {
  --bg-color: #fff;
  --text-color: #000;
}
body.dark-mode {
  --bg-color: #000;
  --text-color: #fff;
}
body {
  background-color: var(--bg-color);
  color: var(--text-color);
}


✔ Light aur dark theme toggle karna easy ho jata hai.

31. How to create a responsive image gallery using CSS Grid?

Answer:

.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-gap: 10px;
}


✔ Automatically images screen size ke hisaab se adjust ho jati hain.

32. How to implement a sticky sidebar without JavaScript?

Answer:

.sidebar {
  position: sticky;
  top: 20px;
}


✔ Sidebar scroll karte waqt top se 20px distance par fix rahega.

33. How to prevent content overflow inside containers?

Answer:

.container {
  overflow-x: hidden;
}


✔ Horizontal scroll aur layout break hone se bachata hai.

34. How to style scrollbars across different browsers?

Answer:

/* For Chrome, Edge, Safari */
::-webkit-scrollbar {
  width: 8px;
}
::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 4px;
}


✔ Cross-browser styling ke liye vendor prefixes aur fallback techniques ka use karna padta hai.


35. Explain how CSS multi-column layout kaam karta hai aur kab use karte hain?

Answer:
Multi-column layout text ko multiple columns mein distribute karta hai, newspaper style ke liye use hota hai.

.container {
  column-count: 3;
  column-gap: 20px;
}


✔ Large amount of text ko readable banane ke liye use hota hai.

36. How do you handle overlapping content in CSS?

Answer:
✔ position aur z-index ka use karke layers control karte hain.
✔ Negative margins ya transform se content ko overlap kar sakte hain.
✔ Overflow control aur clipping (overflow: hidden) se unwanted content hide karte hain.

37. How to create a CSS-only tooltip that appears on hover?

Answer:

.tooltip {
  position: relative;
}
.tooltip:hover .tooltip-text {
  visibility: visible;
  opacity: 1;
}
.tooltip-text {
  position: absolute;
  bottom: 100%;
  background: black;
  color: white;
  padding: 5px;
  visibility: hidden;
  opacity: 0;
  transition: opacity 0.3s ease;
}


✔ User ko extra information show karne ke liye helpful.

38. Explain how you can make an element sticky but only within a parent container.

Answer:
✔ position: sticky; use karne par parent container ke andar hi scroll ke saath fixed behavior milta hai.
✔ top ya bottom offset define karna zaruri hai.

39. How does the CSS overflow property work with scrollbars?

Answer:
✔ overflow: auto; zarurat padne par scrollbar show karega.
✔ overflow: scroll; hamesha scrollbar dikhayega chahe content chhota ho.
✔ overflow: hidden; extra content ko hide kar deta hai.

✅ Animations & Effects Questions
40. How can you animate a hover effect smoothly?

Answer:
✔ transition property use karo.

.button {
  transition: background-color 0.3s ease, transform 0.3s ease;
}
.button:hover {
  background-color: red;
  transform: scale(1.1);
}


✔ Smooth transition user experience ko improve karta hai.

41. Explain how CSS filters like blur, brightness, contrast work.

Answer:
✔ filter: blur(5px); content ko soft dikhata hai.
✔ filter: brightness(150%); brightness badhata hai.
✔ filter: contrast(120%); contrast ko enhance karta hai.
Animation ke liye bhi use kar sakte hain.

42. How do you create a bouncing animation using CSS?

Answer:

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}
.ball {
  animation: bounce 1s infinite;
}


✔ Simple bounce effect jo engaging lagta hai.

43. What are the pros and cons of using CSS animations vs JavaScript animations?

Answer:
Pros CSS animations:
✔ Easy to implement
✔ GPU acceleration available
✔ Less code

Cons:
❌ Complex interactions mein limited
❌ JavaScript jitna flexible nahi

JavaScript animations:
✔ Full control
✔ Interactive aur condition-based animations possible

✅ Selectors, Specificity & Advanced Styling Questions
44. How does CSS inheritance work?

Answer:
✔ Kuch properties jaise color, font-family, line-height automatically parent se child tak inherit hoti hain.
✔ Baaki properties inherit nahi hoti unless explicitly specify karo (inherit value use karo).

45. What is the difference between em and rem units?

Answer:
✔ em: parent element ke font size ke relative hota hai.
✔ rem: root element (<html>) ke font size ke relative hota hai.
Example:

div { font-size: 2em; }
span { font-size: 1.5rem; }


✔ Responsive typography mein helpful.

46. Explain how pseudo-elements ::before and ::after kaam karte hain.

Answer:
✔ Ye extra content inject karte hain without markup badle.
Example:

button::after {
  content: ' →';
}


✔ Stylish effects ke liye useful.

47. How to hide an element from screen readers but keep it visible on screen?

Answer:
✔ Use aria-hidden="true" or specific CSS techniques like:

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
}


✔ Accessibility maintain karne ke liye zaruri.

✅ Performance Optimization Questions
48. Why should you avoid animations on layout-changing properties?

Answer:
✔ width, height, margin, padding par animation karne se layout reflow hota hai → performance slow ho sakti hai.
✔ Instead use transform aur opacity.

49. How do you reduce CSS file size?

Answer:
✔ Unused selectors hatao
✔ Shorthand properties use karo
✔ Variables aur mixins ka use karo
✔ Minify CSS before deployment

50. What is the impact of too many CSS selectors on rendering?

Answer:
✔ Browser ko zyada time lagega apply karne mein
✔ Page slow ho sakta hai
✔ Specificity conflicts create honge
✔ Clean aur optimized CSS zaruri hai

✅ Debugging & Real-World Problems
51. How do you debug CSS layout issues in browser?

Answer:
✔ Inspect element use karo
✔ Box model highlight dekho
✔ Computed styles check karo
✔ Media query breakpoints verify karo
✔ Layout borders aur background temporarily apply karke dekho

52. How to fix margin collapsing problem?

Answer:
✔ Padding ya border add karo
✔ Overflow use karo (overflow: hidden;)
✔ Flexbox layout ka use karo

53. How can you ensure consistent layout across browsers?

Answer:
✔ CSS reset ya normalize stylesheet use karo
✔ Vendor prefixes apply karo
✔ Test on multiple devices aur screen sizes

54. Explain how you can style form elements for consistent appearance.

Answer:
✔ Default browser styles override karo
✔ Padding, border, font-size uniform set karo
✔ Appearance property (appearance: none;) use karke styling start karo from scratch

✅ Security & Best Practices
55. Why should you avoid using !important everywhere?

Answer:
✔ Specificity problems create hoti hain
✔ Maintenance mushkil ho jata hai
✔ Future changes par unexpected issues aa sakte hain

56. How to prevent layout shifts and cumulative layout shift (CLS) issues?

Answer:
✔ Image dimensions define karo
✔ Fonts preload karo
✔ CSS animations use karo jo layout ko break na karein
✔ Avoid dynamic content jo page reflow kare

57. What are deprecated CSS properties and how to handle them?

Answer:
✔ Deprecated properties naye browsers mein support nahi hoti
✔ CSS validators use karo
✔ Modern alternatives dhoondo jaise float ki jagah Flexbox ya Grid

58. How does CSS handle margin collapsing and kaise solve karte hain?

Answer:
Jab do vertical margins ek dusre ke saath touch karte hain to woh collapse ho jaate hain aur bada wala margin apply hota hai.
Solution:
✔ Padding ya border add karo
✔ Overflow use karo (overflow: hidden)
✔ Flexbox layout ka use karo jo margin collapse ko avoid karta hai.

59. Explain how CSS’s contain property improve performance.

Answer:
contain browser ko batata hai ki element ka layout, paint aur size dusre elements ko affect nahi karega.
Example:

.card {
  contain: layout paint size;
}


✔ Repaint aur layout calculations ko optimize karta hai → performance better hoti hai.

60. What is the difference between initial, inherit, and unset?

Answer:
✔ initial: property ko uske default browser value pe reset karta hai.
✔ inherit: property ko parent se inherit karne ko force karta hai.
✔ unset: inherit ya initial dono mein se appropriate value le leta hai.

61. Explain how aspect-ratio property works.

Answer:
Yeh property element ka width aur height ratio fix karti hai.
Example:

.box {
  aspect-ratio: 16 / 9;
}


✔ Video players, images, aur cards mein use hoti hai.

62. How do you create a responsive typography system using CSS?

Answer:
✔ clamp() ka use karke min, preferred aur max size define kar sakte hain.
Example:

h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);
}


✔ Mobile aur desktop dono ke liye responsive font size set hota hai.

➤ Animations & Effects
63. How to chain multiple animations using CSS?

Answer:
✔ animation-name, animation-duration, animation-delay ko comma se separate karke chain kar sakte hain.
Example:

.box {
  animation: fadeIn 2s ease, moveUp 3s ease 2s;
}


✔ Sequential animation create hoti hai.

64. How to trigger animation only once on page load?

Answer:
✔ animation-iteration-count: 1 use karo.
✔ JavaScript se class toggle karne ki zarurat nahi hoti agar sirf load par effect chahiye.

65. What is repaint and reflow in CSS animations?

Answer:
✔ Reflow: layout change hone par page dobara calculate karta hai (width, height, margin etc.).
✔ Repaint: sirf color ya visual change hone par browser repaint karta hai without layout calculation.

66. How to create parallax scrolling effect without JavaScript?

Answer:
✔ background-attachment: fixed ka use karo ya
✔ CSS transform ke saath scroll position simulate karo.

Example:

.parallax {
  background-image: url('image.jpg');
  background-attachment: fixed;
  background-size: cover;
}

67. Explain how perspective and transform-style affect 3D animations.

Answer:
✔ perspective viewer ke distance ko define karta hai → z-axis depth effect create karta hai.
✔ transform-style: preserve-3d; se child elements 3D space mein maintain rehte hain.

➤ Selectors & Specificity
68. How to write selectors that are both efficient and maintainable?

Answer:
✔ Avoid deep nesting
✔ Use classes instead of tag selectors
✔ Avoid universal selector *
✔ Consistent naming convention use karo like BEM (block__element--modifier)

69. Explain how attribute selectors work and kab use karte hain?

Answer:
✔ Attribute selectors element ke kisi attribute ke value ke basis par styling karte hain.
Example:

input[type="text"] {
  border: 1px solid #ccc;
}


✔ Forms ya dynamic content mein helpful hota hai.

70. What is the CSS cascade and how does it resolve conflicting styles?

Answer:
✔ Styles priority hierarchy follow karte hain:

Inline styles

IDs

Classes

Element selectors
✔ Agar specificity same ho to last defined rule apply hota hai.

71. Explain how pointer-events property works.

Answer:
✔ pointer-events: none; se element mouse events ignore karega.
✔ Useful jab aap layered elements mein interactivity control karna chahte ho.

➤ Variables & Theming
72. How to create a CSS theme switcher using variables only?

Answer:
✔ Different themes define karo aur body class ke through switch karo.
Example:

:root {
  --bg: white;
  --text: black;
}
body.dark {
  --bg: black;
  --text: white;
}
body {
  background-color: var(--bg);
  color: var(--text);
}


✔ Easily theme toggle ho sakta hai.

73. How to fallback CSS variable if not supported in browser?

Answer:

color: var(--main-color, blue);


✔ Agar --main-color define nahi hai to blue default apply hoga.

➤ Performance & Debugging
74. Why use will-change property and kab use karna chahiye?

Answer:
✔ Browser ko batata hai ki future mein kaunsi property change hogi → pre-render optimization milta hai.
✔ Overuse mat karo, warna unnecessary memory consume karega.

75. How do you find CSS rendering bottlenecks?

Answer:
✔ Browser dev tools mein paint aur layout times check karo
✔ Unused CSS identify karo
✔ Complex selectors ya deep nesting avoid karo
✔ Animation properties monitor karo

76. Explain cumulative layout shift (CLS) aur kaise avoid karte hain?

Answer:
✔ Layout shift tab hota hai jab content load ke dauran jagah badalti hai
✔ Fix karo: image dimensions define karo, fonts preload karo, transition mein layout properties avoid karo.

77. How to debug specificity issues in CSS?

Answer:
✔ Browser dev tools se computed styles check karo
✔ Identify karo kaunsa rule override ho raha hai
✔ Specificity score calculate karo – ID > class > element
✔ !important ka misuse avoid karo

➤ Accessibility
78. How to ensure that animations don’t disturb people with motion sensitivity?

Answer:
✔ Media query prefers-reduced-motion ka use karo
✔ Slow ya fade transitions choose karo
✔ Layout shift wale animations avoid karo

79. Why focus styles important hote hain and kaise implement karte hain?

Answer:
✔ Keyboard navigation mein users ko pata chalta hai kaunsa element active hai
✔ Default outline visible rakho ya custom accessible styles apply karo
Example:

button:focus {
  outline: 2px solid #000;
}

80. How can contrast ratio affect readability?

Answer:
✔ Text aur background ke beech contrast kam ho to padhna mushkil hota hai
✔ WCAG guidelines ke mutabik sufficient contrast ensure karna zaruri hai

✅ Real-World Problem Solving
81. How to style form validation messages using CSS only?

Answer:
✔ :invalid, :valid pseudo-classes use karo
Example:

input:invalid {
  border-color: red;
}
input:valid {
  border-color: green;
}

82. How to create a skeleton loader using CSS animations?

Answer:
✔ Placeholder elements create karo aur keyframes se gradient animation apply karo
Example:

.skeleton {
  background: linear-gradient(90deg, #eee 25%, #ddd 50%, #eee 75%);
  background-size: 200% 100%;
  animation: loading 1.5s infinite;
}
@keyframes loading {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}

83. Explain how you would make a modal scrollable only if content exceeds viewport.

Answer:
✔ Max height aur overflow-y: auto; use karo

.modal {
  max-height: 80vh;
  overflow-y: auto;
}

84. How to make images responsive using CSS?

Answer:
✔ width: 100%; aur height: auto; use karo
✔ Container ke size ke according adjust ho jayega

85. Explain how you can create a CSS-only hamburger menu toggle.

Answer:
✔ Checkbox hack use karo

<input type="checkbox" id="menu-toggle" />
<label for="menu-toggle">Menu</label>
<nav class="menu">...</nav>


✔ CSS mein :checked pseudo-class se menu open/close kar sakte hain.

86. How to implement a fallback font stack properly?

Answer:
✔ Primary font ke baad secondary aur generic fonts define karo
Example:

body {
  font-family: 'Roboto', Arial, sans-serif;
}


✔ Agar first font load nahi hota to alternate apply hoga.

87. How can CSS custom properties be updated dynamically using JavaScript?

Answer:
✔ CSS variables ko JavaScript se manipulate kar sakte hain
Example:

document.documentElement.style.setProperty('--main-color', 'red');


✔ Theming aur runtime adjustments ke liye helpful.

88. Kaise ensure karte ho ki CSS sab browsers mein kaam kare?

Answer:
✔ Normalize ya reset stylesheet use karo
✔ Vendor prefixes apply karo (-webkit-, -moz-, etc.)
✔ Feature detection karo (@supports)
✔ Testing tools jaise BrowserStack use karo
✔ Progressive enhancement approach follow karo

89. @supports ka use kab aur kaise karte ho?

Answer:
✔ Browser ko test karne ke liye kiya jata hai ki property supported hai ya nahi
Example:

@supports (display: grid) {
  .container {
    display: grid;
  }
}


✔ Fallback styling ke liye helpful

90. Kaise handle karte ho jab kisi property ka browser support limited ho?

Answer:
✔ Feature queries (@supports)
✔ Graceful degradation (optional effects)
✔ JavaScript fallback
✔ Vendor prefixes use karna

➤ Debugging
91. Kaise pata lagate ho ki CSS apply ho raha hai ya nahi?

Answer:
✔ Browser dev tools ka “Computed” tab check karo
✔ Element inspect karke dekho kaunsa rule active hai
✔ Overridden styles highlight hoti hain
✔ Network tab mein CSS file load check karo

92. Agar layout break ho raha hai to kya steps follow karoge?

Answer:
✔ Box model inspect karo
✔ Margin collapse check karo
✔ Parent container ka size dekho
✔ Overflow ya padding issues check karo
✔ Media queries properly trigger ho rahi hain ya nahi dekho

➤ Advanced Selectors
93. Explain how CSS combinators like >, +, ~ kaam karte hain.

Answer:
✔ > direct child ko select karta hai
✔ + adjacent sibling ko select karta hai
✔ ~ general sibling ko select karta hai

Example:

div > p { color: red; }  
h1 + p { margin-top: 10px; }  
ul ~ p { font-size: 14px; }

94. How does :not() pseudo-class help in styling?

Answer:
✔ Exclude elements ko style karne mein help karta hai
Example:

button:not(.primary) {
  background-color: grey;
}


✔ Complex styling mein kaafi useful

➤ Animations
95. How to control animation play state in CSS?

Answer:
✔ animation-play-state se animation ko pause ya resume kar sakte ho
Example:

.box {
  animation: move 2s infinite;
}
.box:hover {
  animation-play-state: paused;
}


✔ User interaction par animation stop karne ke liye helpful

96. Explain how transform-origin affects animations.

Answer:
✔ Transformation ka axis define karta hai
Example:

.box {
  transform-origin: top left;
  transform: rotate(45deg);
}


✔ Rotation ya scaling mein anchor point control karta hai

97. How to combine CSS variables with animations?

Answer:
✔ Variable ko animation keyframe mein use kar sakte hain
Example:

:root {
  --rotate-angle: 45deg;
}
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(var(--rotate-angle)); }
}


✔ Dynamic animations create karne mein kaafi flexible

➤ Performance
98. Why avoid animating top, left and prefer transform?

Answer:
✔ top, left change karne par layout reflow hota hai → performance slow hoti hai
✔ transform GPU accelerated hota hai → smooth animation milti hai

99. How does CSS containment (contain) improve rendering?

Answer:
✔ Browser ko batata hai ki element ka layout aur paint dusron ko affect nahi karega
✔ Isse repaint aur layout calculations optimize hote hain

100. What is critical CSS and how does it improve page load time?

Answer:
✔ Above-the-fold content ke liye sirf zaruri CSS inline ya preload karke page jaldi visible karte hain
✔ Rest CSS ko defer ya async load karte hain

➤ Accessibility
101. How to ensure CSS doesn’t interfere with screen readers?

Answer:
✔ Hidden elements ko aria-hidden="true" use karo
✔ Important content ko visibility se hide mat karo
✔ Focus outlines ko maintain rakho

102. Explain how CSS animations can cause motion sickness and how to prevent it.

Answer:
✔ Excessive animations ya abrupt movement user ko disorient kar sakti hain
✔ prefers-reduced-motion query ka use karke animations slow ya disable karo

103. Why consistent spacing and alignment improve usability?

Answer:
✔ Readability aur visual flow better hota hai
✔ Content cluttered nahi lagta
✔ User experience smooth hota hai

➤ Real-World CSS Problems
104. How to create a responsive navbar without JavaScript?

Answer:
✔ Checkbox hack aur media queries ka use karo
✔ Collapse aur expand layout CSS se control karo

105. How to handle different screen orientations using CSS?

Answer:
✔ @media (orientation: landscape) ya @media (orientation: portrait) ka use karo
✔ Layout orientation ke hisaab se adjust karo

106. Explain how CSS grid layout can be used for masonry layout.

Answer:
✔ grid-auto-flow: dense; aur dynamic row height use karke masonry effect achieve kar sakte hain
✔ Flexible layout ke liye perfect hai

107. How to debug layout break after adding new elements dynamically?

Answer:
✔ Inspect box model aur overflow check karo
✔ Parent container ke flex/grid properties ko revalidate karo
✔ Media queries ko ensure karo ke naye elements ke hisaab se adjust ho rahe hain

✅ Best Practices
108. Why should you use rem over px for fonts?

Answer:
✔ Accessibility aur responsiveness ke liye rem better hai
✔ User ke browser settings ke hisaab se size adjust hota hai

109. Explain why CSS should be modular and reusable.

Answer:
✔ Maintainable aur scalable code milta hai
✔ Future updates easy hote hain
✔ DRY principle follow hota hai

110. How do CSS frameworks like Tailwind or Bootstrap improve development speed?

Answer:
✔ Predefined utility classes milti hain
✔ Responsive aur accessible components ready hote hain
✔ Time aur effort dono save hota hai

111. How to organize CSS for large projects?

Answer:
✔ Component-based structure
✔ Variables aur mixins separate files mein
✔ Naming conventions follow karo (BEM, SMACSS, ITCSS)


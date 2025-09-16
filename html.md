1. HTML5 aur purane HTML mein kya differences hain?
Answer:
HTML5 semantic tags deta hai jaise <article>, <section>, <nav>, <header>, <footer>.
Multimedia support jaise <audio>, <video>.
Local storage (localStorage, sessionStorage).
Offline applications aur form validation mein improvements.
Canvas aur SVG graphics ka support.

2. Semantic HTML kya hota hai aur kyun zaruri hai?
Answer:
Semantic HTML wo tags hote hain jo content ka meaning batate hain. 
Jaise <article> article ke liye, <nav> navigation ke liye. 
Ye SEO improve karta hai, accessibility (screen reader) ko support karta hai, aur maintainable code banata hai.

3. Form validation kaise hoti hai bina JavaScript ke?
Answer:
HTML5 mein built-in attributes hain:
required – field empty nahi chhod sakte.
type="email" – valid email format hona chahiye.
pattern="[A-Za-z]{3,}" – custom regex validation.
min, max, step – number input ke liye.

4. Difference between <div> aur <span>?
Answer:
<div> block-level element hai → pura line le leta hai.
<span> inline element hai → sirf jitna content hai utna space leta hai.

5. Cross-Origin Resource Sharing (CORS) ka HTML se kya connection hai?
Answer:
Agar kisi page mein external resource load karna hai (API ya image), 
browser security ke karan restrictions hoti hain. 
HTML mein <script> ya <img> tag mein CORS headers define nahi hote,
par browser server se response ke CORS headers check karta hai. 
Backend aur browser dono ka role hota hai.

6. HTML mein accessibility ke liye kya best practices hain?
Answer:
alt attribute images ke liye.
Semantic elements use karna.
Form inputs ke liye <label> tag.
Keyboard navigation ka dhyan rakhna.
ARIA attributes ka use (jaise aria-label, aria-hidden).
Contrast aur font size sahi rakhna.


7. DOCTYPE kya hota hai aur HTML mein kyun zaruri hai?
Answer:
DOCTYPE browser ko batata hai kis version ke HTML ka use ho raha hai.
Agar define nahi karenge to browser quirks mode mein chale jayega aur layout distort ho sakta hai.
HTML5 ke liye use: <!DOCTYPE html>.

8. HTML forms mein enctype attribute kya karta hai?
Answer:
enctype batata hai data ka format server ko kaise bhejna hai:
application/x-www-form-urlencoded – default.
multipart/form-data – files upload karne ke liye.
text/plain – plain text format.

9. Difference between id aur class?
Answer:
id unique hota hai page mein sirf ek baar.
class multiple elements ke liye use hota hai.

10. HTML mein <template> tag kya hota hai?
Answer:
Ye ek invisible block hai jo DOM mein nahi dikhai deta jab tak JavaScript se usko clone
ya render na karein. Reusable components banane mein helpful.

11. Difference between localStorage, sessionStorage aur cookies?
Answer:
Storage Type	              Data Expiry	                                     Storage Size	Accessible By

localStorage	     Browser close hone ke baad bhi rehta hai	                        ~5MB	         JavaScript

sessionStorage	           Tab band hote hi delete	                                ~5MB	         JavaScript

cookies	                    Server aur client dono	                                ~4KB	         Server + JS

12. HTML mein meta tags ka use kya hai?
Answer:
SEO, responsive design aur browser behavior control karne ke liye:
<meta charset="UTF-8"> → encoding set karta hai.
<meta name="viewport" content="width=device-width, initial-scale=1.0"> → mobile responsiveness.
<meta name="description" content="..."> → SEO description.

13. How does the <iframe> work aur iske security issues kya hain?
Answer:
<iframe> se kisi aur page ko current page mein embed kar sakte hain.
 Lekin iska misuse clickjacking, data theft ya phishing ke liye ho sakta hai.
 sandbox attribute aur CSP headers use karke security enforce kar sakte hain.

14. Web components kya hain aur kaise use hote hain?
Answer:
Custom HTML elements banane ka tareeka hai. Web Components mein 3 concepts hain:
Custom Elements → apna tag define karo.
Shadow DOM → encapsulated styling aur structure.
HTML Templates → reusable markup.

15. Progressive Web App (PWA) ka HTML mein kya role hai?
Answer:
Manifest file aur service worker ke through web app ko offline support,
 push notifications, aur app-like experience diya jaata hai.

16. Agar ek form mein method="GET" hai to data URL mein kaise dikhega?
Answer:
Jab form ka method GET hota hai to form mein jo bhi data enter kiya jata hai, 
wo URL ke query string mein append ho jata hai.
Example:
<form method="GET" action="https://example.com/search">
  <input type="text" name="query" value="laptop">
  <input type="submit" value="Search">
</form>

17. iframe mein load hone wale content ka origin alag ho to kya issues aayenge?
Answer:
Agar iframe ka content kisi alag domain (origin) se load ho raha hai, 
to browser Same-Origin Policy enforce karta hai. Iska matlab:
✔ Tum parent page se iframe ke andar ke content ko directly access nahi kar sakte.
✔ Cross-site scripting attacks (XSS) ko rokne ke liye security restrictions hoti hain.
✔ Data exchange ke liye postMessage() ka use karna padta hai.
Example:
<iframe src="https://otherdomain.com/page.html"></iframe>

18. picture tag ka use kab aur kaise hota hai?
Answer:
<picture> tag ka use responsive images dikhane ke liye hota hai – jaise screen size,
 resolution, format ke hisaab se alag image load karna.
Example:
<picture>
  <source media="(max-width: 600px)" srcset="small-image.jpg">
  <source media="(min-width: 601px)" srcset="large-image.jpg">
  <img src="default-image.jpg" alt="Example Image">
</picture>

19. data- attributes kya hote hain aur kaise use karte hain?*
Answer:
data-* attributes custom attributes hote hain jo tum apne HTML elements mein extra
 data store karne ke liye use kar sakte ho. JavaScript mein easily access kar sakte ho.
Example:
<div id="product" data-id="101" data-category="electronics">
  Smart TV
</div>

JavaScript se access:
const product = document.getElementById('product');
console.log(product.dataset.id);        // Output: 101
console.log(product.dataset.category);  // Output: electronics

20. SEO optimize HTML ka structure kaisa hona chahiye?
Answer:
SEO-friendly HTML ka structure user experience aur search engine dono ke liye optimized hota hai.
Best Practices:
✔ Semantic tags use karo:
<header>, <nav>, <main>, <article>, <section>, <footer>

✔ Title tag meaningful ho:
<title>Buy Best Smart TVs Online - ExampleStore</title>

✔ Meta description include karo:
<meta name="description" content="ExampleStore par smart TVs, best price aur fast delivery ke saath. Aaj hi order karein.">

✔ Headings ka structure sahi rakho:
<h1> sirf ek baar use karo page ka main topic define karne ke liye.
<h2>, <h3> se subsections banao.

✔ Alt text use karo images ke liye:
<img src="tv.jpg" alt="Latest Smart TV model">

✔ Mobile-friendly viewport include karo:
<meta name="viewport" content="width=device-width, initial-scale=1.0">

✔ Fast load time → images compress karo, unnecessary scripts avoid karo.

✔ Structured data use kar sakte ho (JSON-LD format mein) taki search engine page ko achhi tarah samajh sake.

21. Difference between <script> tag ka defer aur async attribute mein kya hai?
Answer:
Jab tum JavaScript file ko HTML mein include karte ho to browser usko kab 
aur kaise load kare ye control karne ke liye defer aur async attributes use karte hain.

Attribute                  Kya karta hai	                                                                                       Kab execute hota hai
defer                      Script ko load karne ke baad page ka parsing complete hone par execute karta hai	                   HTML parse hone ke baad, order mein execute
async	                     Script ko load aur parse parallel mein karta hai, jaise hi load ho jaye, execute karta hai	         Jis waqt load ho, tab execute, order ka dhyan nahi

Example:
<script src="script1.js" defer></script>
<script src="script2.js" defer></script>

→ Dono parse hone ke baad order mein execute honge.
<script src="script1.js" async></script>
<script src="script2.js" async></script>

22. HTML mein contenteditable attribute kya hota hai aur kaise use karte hain?
Answer:
contenteditable attribute kisi bhi element ko editable bana deta hai. User directly browser mein content ko edit kar sakta hai.
Example:
<div contenteditable="true">
  Is text ko tum edit kar sakte ho.
</div>

Use Cases:
✔ WYSIWYG editor banana.
✔ Notes ya comments inline edit karne ke liye.
✔ Dynamic UI jahan user content customize kare.

23. <noscript> tag kya hota hai aur iska use kab hota hai?
Answer:
<noscript> tag ka use tab hota hai jab kisi user ka browser JavaScript support nahi karta ya 
usne JavaScript disable kar diya ho. Is tag ke andar likha content sirf tab dikhai deta hai jab JavaScript available na ho.
Example:
<noscript>
  <p>Please enable JavaScript to use this website properly.</p>
</noscript>

Use Cases:
✔ Users ko inform karna agar JavaScript disabled hai.
✔ Fallback content dikhana.
✔ SEO ke liye helpful – kyunki kuch crawlers JavaScript process nahi karte.

24. <base> tag kya karta hai aur isko use karne ka fayda kya hai?
Answer:
<base> tag HTML document mein base URL ya default target define karta hai,
 jisse relative links aur resources ka path automatically us base URL ke hisaab se resolve hota hai.
Example:
<base href="https://example.com/assets/" target="_blank">
<a href="image.jpg">View Image</a>

Is case mein link automatically is URL par redirect karega:
https://example.com/assets/image.jpg
Use Cases:
✔ Relative paths ko manage karna.
✔ Links ko naye tab mein open karna.
✔ Large projects mein maintainability improve karna.

25. HTML mein aria-* attributes kya hote hain aur kaise use karte hain?
Answer:
aria-* attributes accessibility improve karne ke liye use hote hain, taaki screen readers
aur assistive devices ko content samajhne mein madad mile. ARIA ka full form hai Accessible Rich Internet Applications.
Common attributes:
✔ aria-label → element ko naam dene ke liye.
✔ aria-hidden="true" → element ko screen readers se hide karne ke liye.
✔ aria-expanded="false" → batata hai ki koi dropdown ya collapsible section open hai ya nahi.
✔ aria-live="polite" → jab content update ho to screen reader ko batata hai.

Example:
<button aria-label="Close menu" onclick="closeMenu()">X</button>
<div aria-live="polite">
  New notifications will appear here.
</div>

Use Cases:
✔ Visually impaired users ke liye navigation aur content accessible banana.
✔ Dynamic content updates ko announce karna.
✔ Custom UI components ko screen reader-friendly banana.

26. <meta http-equiv> attribute kya karta hai aur iska use kyun karte hain?
Answer:
<meta http-equiv> HTTP headers ko simulate karta hai jo server normally response mein bhejta hai. Isse browser ko specific instructions milte hain.
Common use cases:
✔ Content-Type → character encoding define karna.
✔ refresh → page ko automatically reload ya redirect karna.
✔ X-UA-Compatible → older Internet Explorer versions ke compatibility mode ko control karna.

Example:
<meta http-equiv="refresh" content="5;url=https://example.com/new-page.html">

➡️ Page 5 seconds baad automatically redirect ho jayega.
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

➡️ Browser ko UTF-8 encoding use karne ke liye batata hai.
Use Cases:
✔ Legacy support.
✔ Automatic page refresh ya redirect.
✔ Encoding issues ko solve karna.


27. Difference between block-level elements aur inline elements kya hai?
Answer:
HTML elements do main categories mein divide hote hain: block-level aur inline.
Type	            Behavior	                                                                      Example
Block-level	      Apni alag line mein aata hai, poora width le leta hai	                         <div>, <p>, <h1>, <section>
Inline	          Sirf jitna content hai utna space leta hai, line ke andar hi rehta hai	       <span>, <a>, <strong>, <img>

Example:
<div>This is a block element</div>
<span>This is an inline element</span>
<span>Still inline</span>

➡ Block elements naye line mein dikhte hain, inline elements ek hi line mein rehte hain.
Use Cases:
✔ Layout design mein block elements ka use structure banane ke liye.
✔ Inline elements ka use styling aur text format ke liye.

28. <link> tag ka kya use hai aur kaise kaam karta hai?
Answer:
<link> tag HTML mein external resources ko link karne ke liye use hota hai, jaise CSS stylesheets, fonts, icons etc. Ye page ke head section mein likha jata hai.
Common attributes:
✔ rel="stylesheet" → external CSS file link karne ke liye.
✔ href="file.css" → file ka path specify karne ke liye.
✔ type="text/css" → file ka MIME type define karne ke liye.

Example:
<head>
  <link rel="stylesheet" href="styles.css" type="text/css">
  <link rel="icon" href="favicon.ico" type="image/x-icon">
</head>

Use Cases:
✔ Website ka design aur layout alag CSS file mein rakhna.
✔ Favicons, fonts, theme files link karna.
✔ Performance improve karna – browser cache ka fayda.


29. <iframe> aur <object> tag mein kya difference hai?
Answer:
Dono tags external content ko embed karne ke liye use hote hain, lekin unke use cases aur behavior alag hote hain.
Feature	               <iframe>	                                                              <object>
Purpose	               Ek alag web page ya resource embed karna                              	Kisi bhi media type (HTML, PDF, image, video) embed karna
Browser support	       Sabhi modern browsers mein	                                            Support thoda limited ho sakta hai
Fallback content	     Limited fallback support	                                              <object> ke andar fallback content likh sakte ho
Security               restrictions	Same-origin policy	                                      Same-origin policy, lekin fallback content provide kar sakte ho

Example – iframe:
<iframe src="https://example.com" width="600" height="400"></iframe>

Example – object:
<object data="document.pdf" type="application/pdf" width="600" height="400">
  <p>Your browser does not support embedded PDF. Download it <a href="document.pdf">here</a>.</p>
</object>

Use Cases:
✔ iframe → external web pages embed karne ke liye.
✔ object → multimedia ya documents embed karne ke liye fallback ke saath.


30. <details> aur <summary> tag kya hote hain aur kaise kaam karte hain?
Answer:
Ye tags HTML5 mein diye gaye hain jisse collapsible content block bana sakte hain.
 User jab summary par click kare to details open ya close ho jati hai.

Example:
<details>
  <summary>Read More</summary>
  <p>Yeh additional information hai jo tab dikhegi jab user click karega.</p>
</details>

Behavior:
✔ Default mein content collapse rehta hai.
✔ Summary par click karne par details expand hoti hai.
✔ JavaScript ke bina accordion-type UI banaya ja sakta hai.

Use Cases:
✔ FAQs, tutorials, step-by-step instructions.
✔ Space bachana aur clean UI banana.

31. HTML mein <fieldset> aur <legend> tag ka kya use hai?
Answer:
<fieldset> aur <legend> ka use forms mein groups create karne ke liye hota hai, taaki related form controls ko logically aur visually organize kar sakein.

✔ <fieldset> → Form ke andar fields ko group karta hai, ek box ke andar dikhata hai.
✔ <legend> → Us group ka title ya heading provide karta hai.

Example:
<form>
  <fieldset>
    <legend>Personal Information</legend>
    Name: <input type="text" name="name"><br>
    Email: <input type="email" name="email"><br>
  </fieldset>
</form>

Use Cases:
✔ Forms ko clean aur structured banana.
✔ Accessibility improve karna (screen readers groups ko better samajhte hain).
✔ Visual separation provide karna.

32. <mark> tag kya hota hai aur kab use karte hain?
Answer:
<mark> tag ka use kisi text ko highlight karne ke liye hota hai – jaise search results mein matched keywords ko mark karna.

Example:
<p>Search result: Learn <mark>HTML</mark> in simple steps.</p>

➡ Yahan “HTML” text highlight hoga.
Use Cases:
✔ Important text ya search matches highlight karna.
✔ User ko easily attention draw karwana.
✔ Styling ke liye CSS ke saath aur customization possible hai.

33. HTML mein <progress> tag kya hota hai aur kaise use karte hain?
Answer:
<progress> tag ka use kisi task ke progress ko dikhane ke liye hota hai – jaise file upload, download, form completion, etc.
Attributes:
✔ value → current progress ki quantity.
✔ max → total quantity ya maximum value.

Example:
<label for="fileUpload">File Upload Progress:</label>
<progress id="fileUpload" value="30" max="100">30%</progress>

➡ Ye dikhata hai ki 100 mein se 30 ka progress complete ho chuka hai.
Use Cases:
✔ Upload/download progress.
✔ Form filling indicator.
✔ Games ya tasks mein feedback dena.

34. HTML mein <template> tag ka purpose kya hai aur kaise kaam karta hai?
Answer:
<template> tag ka use reusable HTML structure ko define karne ke liye hota hai jo page load par render nahi hota. 
JavaScript se ise clone karke dynamically content dikhaya ja sakta hai.

Example:
<template id="cardTemplate">
  <div class="card">
    <h2>Title</h2>
    <p>Description goes here.</p>
  </div>
</template>

<div id="container"></div>
<script>
  const template = document.getElementById('cardTemplate');
  const container = document.getElementById('container');
  const clone = template.content.cloneNode(true);
  container.appendChild(clone);
</script>

Use Cases:
✔ Reusable UI components banana.
✔ Performance improve karna (server se baar-baar request nahi karni padti).
✔ Dynamic content insertion.

35. <script> tag mein type="module" ka kya use hai?
Answer:
type="module" likhne par browser file ko ES6 module ke roop mein treat karta hai. Isse tum import/export ka use kar sakte ho.

Example:
<script type="module">
  import { greet } from './utils.js';
  greet();
</script>

Use Cases:
✔ Code ko modular banana.
✔ Reusability aur maintainability improve karna.
✔ Modern JavaScript ka use enable karna.

36. HTML mein custom data attributes ko kaise style kar sakte hain?
Answer:
CSS mein attribute selectors ka use karke data attributes ke basis par styling kar sakte hain.

Example:
<div data-status="active">Active User</div>
<div data-status="inactive">Inactive User</div>

div[data-status="active"] {
  color: green;
}

div[data-status="inactive"] {
  color: red;
}

Use Cases:
✔ Dynamic states ko style karna.
✔ JavaScript se data attributes ke basis par UI change karna.

37. <b> aur <strong> tag mein kya difference hai?
Answer:
✔ <b> sirf text ko visually bold karta hai – meaning nahi batata.
✔ <strong> semantic tag hai jo batata hai ki ye text important hai – SEO aur accessibility mein useful.

Example:
<p>This is <b>bold</b> text but not important.</p>
<p>This is <strong>important</strong> text.</p>

Use Cases:
✔ Design aur meaning dono ko alag rakhna.
✔ Accessibility improve karna.


38. <wbr> tag kya hota hai aur iska kya use hai?
Answer:
<wbr> ka use long text ko break karne ke liye hint dene ke liye hota hai – browser decide karega ki yahan break karna hai ya nahi.

Example:
<p>Visit our website at www.example<wbr>.com for more info.</p>

Use Cases:
✔ URLs, long strings ko properly wrap karna.
✔ Layout break hone se bachana.

39. <abbr> tag kya hota hai aur kaise use karte hain?
Answer:
<abbr> tag ka use abbreviations ya short forms ko define karne ke liye hota hai. title attribute se full form bataya jata hai.

Example:
<p>The <abbr title="Hyper Text Markup Language">HTML</abbr> is widely used.</p>

Use Cases:
✔ SEO aur accessibility mein clarity dena.
✔ Tooltips ke through extra information dikhana.


40. HTML mein comment kaise likhte hain aur iska kya purpose hai?
Answer:
Comments code mein explanation ya notes dene ke liye likhe jaate hain, jo browser render nahi karta.

Syntax:
<!-- Ye ek comment hai -->

Use Cases:
✔ Code ko explain karna.
✔ Future mein changes ya debugging ke liye notes rakhna.
✔ Temporarily code disable karna.

41. <base target="_blank"> ka kya matlab hai?
Answer:
<base target="_blank"> likhne par page ke saare links default roop se naye tab mein open honge.

Example:
<head>
  <base target="_blank">
</head>
<body>
  <a href="https://example.com">Visit Example</a>
</body>

➡ Ye link naye tab mein open hoga.
Use Cases:
✔ Saare external links ko ek jaise behavior dena.
✔ UX control karna.


42. <s>, <del> aur <ins> mein kya fark hai?
Answer:
✔ <s> → text ko strikethrough dikhata hai, style-based.
✔ <del> → text ko delete hua dikhata hai, semantics ke saath.
✔ <ins> → text ko insert hua dikhata hai.

Example:
<p>Old price: <s>$100</s></p>
<p>Discounted price: <del>$100</del> <ins>$80</ins></p>

Use Cases:
✔ Document editing, versioning.
✔ Price changes dikhana.
✔ Historical records maintain karna.

43. <time> tag kya hota hai aur iska kya fayda hai?
Answer:
<time> tag kisi date ya time ko define karta hai, jisse browser aur search engine usko samajh sakein.

Example:
<p>Event date: <time datetime="2025-09-15">15 September 2025</time></p>

Use Cases:
✔ SEO mein structured data provide karna.
✔ User ko readable format aur machines ko parseable format dena.

44. HTML mein <input> types kitne hote hain aur kuch uncommon types ka use kya hai?
Answer:
Common types: text, email, password, submit.
Uncommon types:
✔ color → color picker.
✔ date → date select karne ke liye.
✔ range → slider control.
✔ tel → phone number ke liye.
✔ file → file upload ke liye.

Example:
<input type="color" name="favcolor" value="#ff0000">
<input type="date" name="dob">
<input type="range" name="volume" min="0" max="100">

Use Cases:
✔ User experience enhance karna.
✔ Data validation aur UI improvement.

45. HTML mein <source> tag kya hota hai aur iska use kab karte hain?
Answer:
<source> tag media elements jaise <audio> aur <video> ke andar use hota hai jab tum
 multiple formats ya resolutions dena chahte ho. Browser apni compatibility ke hisaab se sahi file choose karega.

Example:
<video controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

Use Cases:
✔ Video/audio ko cross-browser compatible banana.
✔ Multiple formats provide karke fallback ensure karna.
✔ Performance aur compatibility improve karna.

46. HTML mein <colgroup> aur <col> tag ka kya use hai?
Answer:
<colgroup> aur <col> ka use table mein columns ko group karke unki styling ya attributes set karne ke liye hota hai.

Example:
<table border="1">
  <colgroup>
    <col span="2" style="background-color: lightgrey">
    <col style="background-color: lightblue">
  </colgroup>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>Country</th>
  </tr>
  <tr>
    <td>Ashish</td>
    <td>25</td>
    <td>India</td>
  </tr>
</table>

➡ Is example mein pehle do columns light grey aur teesra column light blue background mein dikhega.
Use Cases:
✔ Tables ko visually organize karna.
✔ Columns ka styling alag-alag dena.
✔ Complex tables mein structure improve karna.


47. <canvas> tag kya hota hai aur isko kaise use karte hain?
Answer:
Canvas ek drawable area hai jahan tum graphics, shapes, animation, charts, games create kar sakte ho JavaScript ke through.

Example:
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #000000;"></canvas>

<script>
  const canvas = document.getElementById('myCanvas');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = "red";
  ctx.fillRect(20, 20, 150, 50);
</script>

Use Cases:
✔ Games, charts, animations banana.
✔ Graphics draw karna without external libraries.

48. <iframe> ke security issues ko kaise handle karte hain?
Answer:
✔ sandbox attribute use karke scripts block kar sakte hain.
✔ CSP headers se unsafe content block karte hain.
✔ referrerpolicy set karke privacy control karte hain.

Example:
<iframe src="https://example.com" sandbox="allow-scripts allow-same-origin" referrerpolicy="no-referrer"></iframe>

Use Cases:
✔ Clickjacking se bachav.
✔ Cross-origin attacks prevent karna.

49. <meta charset="UTF-8"> ka use kyun zaruri hai?

Answer:
Yeh browser ko batata hai ki page ka encoding UTF-8 hai,
 jo almost sab languages ko support karta hai. Isse text rendering errors nahi hote.

Use Cases:
✔ Special characters ka sahi display.
✔ Global audience ke liye compatibility.

50. HTML mein role attribute kya hota hai?
Answer:
role attribute assistive technologies ko batata hai ki element ka purpose kya hai – jaise button, navigation, main, etc.

Example:
<div role="navigation">
  <a href="#">Home</a>
  <a href="#">About</a>
</div>

Use Cases:
✔ Accessibility improve karna.
✔ Semantic meaning provide karna jab standard tags available na ho.

51. <link rel="preload"> ka use kya hai?
Answer:
Isse browser ko batate hain ki kaunsa resource jaldi load karna hai taaki performance improve ho.

Example:
<link rel="preload" href="style.css" as="style">

Use Cases:
✔ Critical CSS ya fonts ko jaldi load karwana.
✔ Page speed improve karna.

52. HTML mein <dialog> tag kya hai?
Answer:
<dialog> tag modal ya popup banane ke liye use hota hai jo automatically style aur functionality deta hai.

Example:
<dialog id="myDialog">
  <p>This is a dialog box.</p>
  <button onclick="document.getElementById('myDialog').close()">Close</button>
</dialog>

<button onclick="document.getElementById('myDialog').showModal()">Open Dialog</button>

Use Cases:
✔ Popups, confirmations, forms.
✔ JavaScript se easily control karna.

53. HTML mein <script> ko <head> ya <body> mein rakhne ka kya farak hai?
Answer:
✔ <head> mein rakha to page parse hone se pehle script load hoga – blocking behavior ho sakta hai.
✔ <body> ke end mein rakha to pehle content load hoga, script baad mein chalega.

Best Practice:
✔ defer attribute use karke dono jagah safe load kar sakte ho.

54. HTML mein <bdo> tag kya hai aur kab use karte hain?
Answer:
<bdo> tag text ka direction override karta hai – left-to-right ya right-to-left.

Example:
<bdo dir="rtl">Yeh text right se left likha gaya hai.</bdo>

Use Cases:
✔ Arabic, Hebrew jaise languages ka support.
✔ UI layout customize karna.

55. <iframe> aur <embed> mein kya fark hai?
Answer:
✔ <iframe> mostly web pages embed karta hai.
✔ <embed> videos, PDFs, media objects embed karta hai.

Example:
<embed src="file.pdf" type="application/pdf" width="500" height="400">

Use Cases:
✔ Multimedia content embed karna.
✔ Interactive documents dikhana.

56. <output> tag kya hota hai aur iska use kab hota hai?
Answer:
<output> tag result dikhane ke liye use hota hai – jaise form submission ka result ya calculation output.

Example:
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="range" id="a" value="50"> +
  <input type="number" id="b" value="50">
  = <output name="result" for="a b">100</output>
</form>

Use Cases:
✔ Real-time calculations dikhana.
✔ User-friendly forms banana.

57. <meter> tag kya hai aur iska use kab hota hai?
Answer:
<meter> tag kisi scalar measurement ko dikhata hai – jaise battery level, progress, rating etc.

Example:
<meter value="0.6" min="0" max="1">60%</meter>

Use Cases:
✔ Percentage, rating, health indicators.
✔ Data visualization mein use.

58. <picture> aur <img> tag mein kya fark hai?
Answer:
✔ <img> single image dikhata hai.
✔ <picture> responsive aur multiple formats support karta hai.

Use Cases:
✔ Performance optimize karna.
✔ Cross-browser compatibility ensure karna.

59. HTML mein forms ke liye autocomplete kaise use karte hain?
Answer:
autocomplete="on" ya autocomplete="off" attributes se browser ko suggest ya disable karne ke liye batate hain.

Example:
<form autocomplete="on">
  <input type="email" name="email">
  <input type="password" name="password">
  <input type="submit">
</form>

Use Cases:
✔ User experience improve karna.
✔ Sensitive fields mein autocomplete disable karna.

60. <iframe> ke liye referrerpolicy attribute ka use kya hai?
Answer:
referrerpolicy browser ko batata hai ki request ke saath referer header kaise bhejna hai.

Example:
<iframe src="https://example.com" referrerpolicy="no-referrer"></iframe>

Use Cases:
✔ Privacy protect karna.
✔ Sensitive URLs ko hide karna.


61. <iframe> mein allow attribute kya hota hai?
Answer:
allow attribute se tum specify karte ho ki iframe ko kaunsi permissions milengi – jaise camera, microphone, autoplay etc.

Example:
<iframe src="https://example.com" allow="camera; microphone; autoplay"></iframe>

Use Cases:
✔ Security aur privacy control karna.
✔ Permissions ko explicitly define karna.

62. <svg> tag kya hai aur iska use kab hota hai?
Answer:
SVG ka matlab hai Scalable Vector Graphics. Isse tum resolution-independent images aur shapes draw kar sakte ho.

Example:
Use Cases:
✔ Logos, charts, icons create karna.
✔ Responsive aur crisp graphics banana.

63. <base> tag ko ek page mein sirf ek baar kyu use karte hain?
Answer:
Agar multiple <base> tags use kiye to browser sirf pehla tag consider karega. Multiple base URLs confusion create karenge.

✔ Single source of truth maintain karne ke liye use karte hain.

64. <template> aur <slot> mein kya difference hai?
Answer:
✔ <template> predefined reusable markup store karta hai.
✔ <slot> shadow DOM mein content placeholder hota hai jahan dynamic content inject kiya jata hai.

Use Cases:
✔ Web components banana.
✔ Templates aur content injection manage karna.

65. HTML mein semantic elements ka kya use hai?
Answer:
Semantic elements page structure ko meaningful banate hain – jaise <header>, <footer>, <article>, <nav>.

Example:
<header><h1>My Website</h1></header>
<nav><a href="#">Home</a></nav>
<article><p>Content goes here.</p></article>
<footer>© 2025</footer>

Use Cases:
✔ SEO improve karna.
✔ Accessibility enhance karna.
✔ Code readability aur maintainability better karna.

66. <audio> tag mein controls, autoplay, loop ka kya use hai?
Answer:
✔ controls → play/pause buttons dikhata hai.
✔ autoplay → page load hone par automatically play karta hai.
✔ loop → media khatam hone par dubara start karta hai.

Example:
<audio controls autoplay loop>
  <source src="song.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

Use Cases:
✔ Background music, podcasts, tutorials mein use.

67. <meta name="viewport"> ka kya importance hai?
Answer:
Mobile responsiveness ke liye viewport tag zaruri hai. Isse tum batate ho page ko kaise scale karna hai.

Example:
<meta name="viewport" content="width=device-width, initial-scale=1.0">

Use Cases:
✔ Responsive design ensure karna.
✔ Mobile browsers mein layout correct dikhana.

68. HTML mein character encoding define karna zaruri kyu hai?
Answer:
Agar encoding define nahi ki to browser content ko galat read kar sakta hai – jisse special characters, emojis, ya dusri languages dikhne mein error aa sakta hai.

✔ UTF-8 sabse recommended encoding hai.

69. <progress> aur <meter> mein kya difference hai?
Answer:
✔ <progress> kisi task ki completion dikhata hai – jaise upload progress.
✔ <meter> kisi measurement ko dikhata hai – jaise battery level ya score.

Use Cases:
✔ Alag-alag data visualization needs.

70. <form> mein novalidate ka use kya hai?
Answer:
novalidate attribute browser ke default validation ko disable kar deta hai. Isse tum custom validation implement kar sakte ho.

Example:
<form novalidate>
  <input type="email" required>
  <button type="submit">Submit</button>
</form>

Use Cases:
✔ JavaScript based validation ko prefer karna.

71. <details> ko open kaise rakhte hain by default?
Answer:
open attribute add karke details ko initially expand rakha ja sakta hai.

Example:
<details open>
  <summary>More Info</summary>
  <p>Yeh content open dikhega by default.</p>
</details>

72. <iframe> mein loading="lazy" ka use kya hai?
Answer:
Isse browser tab tak iframe load nahi karega jab tak user usko view area mein scroll na kare – isse performance improve hoti hai.

Example:
<iframe src="https://example.com" loading="lazy"></iframe>

Use Cases:
✔ Page load time reduce karna.
✔ Resource management optimize karna.

73. <meta name="robots"> ka use kya hai?
Answer:
Search engine crawlers ko batane ke liye use hota hai ki page index ho ya nahi, follow links kare ya nahi.

Example:
<meta name="robots" content="noindex, nofollow">

Use Cases:
✔ SEO control karna.
✔ Private pages ko search results se hide karna.

74. <iframe> mein referrerpolicy="origin" ka meaning kya hai?
Answer:
Sirf origin URL referer mein bheja jayega, full path nahi.

✔ Privacy maintain karne ke liye use hota hai.

75. HTML mein accessibility (A11Y) ka importance kya hai?
Answer:
Accessibility ensure karta hai ki disabled ya visually impaired users bhi content access kar saken.

✔ ARIA attributes, semantic tags, keyboard navigation, contrast ratio sab include hote hain.

76. HTML mein <bdi> tag kya hota hai aur iska use kab karte hain?
Answer:
<bdi> ka matlab hai Bi-Directional Isolation. Ye tag browser ko batata hai ki is content ka text direction baaki content se alag treat karein, chahe wo left-to-right ho ya right-to-left.

Example:
<p>Your name is <bdi>علي</bdi> and you're registered.</p>

Use Cases:
✔ Multilingual websites mein direction control karna.
✔ User input ko safely display karna without layout break hue.

77. HTML mein hidden attribute ka kya use hai?
Answer:
hidden attribute kisi element ko temporarily hide kar deta hai. Ye CSS se alag hai, aur browser use content ko render hi nahi karta.

Example:
<div hidden>
  This content is hidden from users and assistive technologies.
</div>

Use Cases:
✔ Conditional content show/hide karna.
✔ Accessibility ke rules follow karna.

78. <link rel="manifest"> ka use kya hai?
Answer:
Iska use Progressive Web Apps (PWA) mein hota hai. Isse browser ko app ka metadata milta hai – jaise naam, icons, theme.

Example:
<link rel="manifest" href="/manifest.json">

Use Cases:
✔ Mobile apps jaise behavior dena.
✔ Installable web apps banana.

79. <noscript> tag ka SEO par kya asar hota hai?

Answer:
Agar tumhare page mein JavaScript heavy content hai, to <noscript> fallback search engines ke liye helpful hota hai.

✔ SEO mein crawling improve karta hai.
✔ Non-JavaScript users ko bhi content milta hai.

80. <abbr> aur <cite> mein kya fark hai?
Answer:
✔ <abbr> short form ko define karta hai.
✔ <cite> kisi source ya reference ka naam batata hai.

Example:
<p>The <abbr title="World Health Organization">WHO</abbr> reports...</p>
<p><cite>The Times</cite>, 2025</p>

Use Cases:
✔ Academic articles, news, research mein reference dena.

81. <form> mein action aur method ka kya use hai?
Answer:
✔ action batata hai ki form submit hone par data kahan bhejna hai.
✔ method batata hai ki data kaise bhejna hai – GET ya POST.

Example:
<form action="/submit-form" method="POST">
  <input type="text" name="username">
  <button type="submit">Submit</button>
</form>

Use Cases:
✔ Data server par bhejna.
✔ Secure forms banana.

82. <input type="hidden"> ka use kya hai?
Answer:
Hidden input user ko dikhai nahi deta, lekin form data ke saath submit hota hai.

Example:
<input type="hidden" name="token" value="abc123">

Use Cases:
✔ CSRF tokens, session info store karna.

83. <details> aur <summary> accessible kaise banate hain?
Answer:
✔ Semantic structure already accessible hota hai.
✔ Ensure karein ki keyboard se expand/collapse ho sake.

Use Cases:
✔ FAQs, guides mein content organization.

84. <mark> aur CSS background-color mein kya fark hai?
Answer:
✔ <mark> semantic highlight hai jo importance batata hai.
✔ background-color sirf style hai.

Use Cases:
✔ Screen readers ko batana ki text highlighted hai.

85. HTML mein data-* attributes ka use kahan hota hai?
Answer:
✔ Extra information store karne ke liye jo JavaScript se access ki ja sakti hai.

Example:
<button data-user-id="101">Profile</button>

Use Cases:
✔ Custom data pass karna.
✔ JavaScript-based UI interactions.

86. <output> aur JavaScript ka integration kaise karte hain?
Answer:
✔ Form fields ke calculations ko dynamic dikhane ke liye.

Example:
<form oninput="result.value=parseInt(a.value) + parseInt(b.value)">
  <input type="number" id="a" value="0">
  <input type="number" id="b" value="0">
  = <output name="result" for="a b">0</output>
</form>

Use Cases:
✔ Real-time feedback forms.

87. HTML mein <template> ka JavaScript se kaise use karte hain?
Answer:
✔ Predefined markup ko clone karke page mein insert karte hain.

Example:
<template id="item-template">
  <li>New Item</li>
</template>

<ul id="list"></ul>

<script>
  const template = document.getElementById('item-template');
  const list = document.getElementById('list');
  const clone = template.content.cloneNode(true);
  list.appendChild(clone);
</script>

Use Cases:
✔ Reusable components banana.
✔ Dynamic content insert karna.

88. <script> mein async aur defer ka kya difference hai?
Answer:
✔ async → script download hote hi execute karega, page parsing ko block kar sakta hai.
✔ defer → script download ke baad page parse hone par execute karega.

Example:
<script src="script.js" async></script>
<script src="script.js" defer></script>

Use Cases:
✔ Page load time optimize karna.

89. HTML mein caching ko kaise manage karte hain?
Answer:
✔ Cache-Control headers se browser ko batate hain resource kab aur kaise cache karna hai.
✔ <meta> se kabhi-kabhi hints diye jaate hain, lekin server-side headers zyada effective hote hain.

90. HTML validation ka importance kya hai?
Answer:
✔ Errors detect karne mein madad karta hai.
✔ Browser compatibility aur SEO improve karta hai.

Use Cases:
✔ Clean code maintain karna.


91. HTML mein <slot> tag kya hai aur kab use hota hai?
Answer:
<slot> tag Web Components mein placeholder ka kaam karta hai. Isse tum parent content ko child component mein inject karte ho.

Example:
<template id="my-template">
  <div>
    <h2>Title</h2>
    <slot></slot>
  </div>
</template>

Use Cases:
✔ Reusable components banana.
✔ Dynamic content injection karna.

92. <track> tag ka use video/audio ke saath kaise hota hai?
Answer:
<track> subtitle, captions, descriptions, chapters jaise extra text content dene ke liye use hota hai.

Example:
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="captions_en.vtt" kind="subtitles" srclang="en" label="English">
</video>

Use Cases:
✔ Accessibility aur usability improve karna.

93. HTML mein autocomplete="off" ka use kahan aur kyu karte hain?
Answer:
Form fields mein autocomplete disable karne ke liye use karte hain, jab sensitive information ho ya custom validation chahiye.

Example:
<form autocomplete="off">
  <input type="password" name="pass">
</form>

Use Cases:
✔ Security ensure karna.
✔ Custom form experience create karna.

94. <b> aur <i> tag ka semantic meaning kya hai?
Answer:
✔ <b> sirf text ko bold dikhata hai – styling ke liye.
✔ <i> italic style deta hai – lekin meaning optional hota hai.

✔ Accessibility aur SEO mein semantic meaning ka use nahi hota, isliye modern tags (<strong>, <em>) zyada recommended hain.

95. HTML mein formnovalidate attribute kya karta hai?
Answer:
Submit button par lagane par ye attribute form ke validation ko bypass kar deta hai.

Example:
<button type="submit" formnovalidate>Submit Without Validation</button>

Use Cases:
✔ Optional forms mein validation skip karna.

96. <meta http-equiv="refresh"> ka use kya hai?
Answer:
Isse page ko automatically refresh ya redirect karne ke liye use karte hain.

Example:
<meta http-equiv="refresh" content="5; url=https://example.com">

➡ 5 seconds baad user ko redirect karega.
Use Cases:
✔ Auto-refresh pages.
✔ Redirect user to another page.

97. HTML mein crossorigin attribute ka kya use hai?
Answer:
Isse cross-origin resource sharing ko control karte hain, jaise images, scripts load karte waqt.

Example:
<img src="https://example.com/image.jpg" crossorigin="anonymous">

Use Cases:
✔ Third-party resources ko securely load karna.
✔ CORS issues ko manage karna.

98. <fieldset> ka disabled attribute kaise kaam karta hai?
Answer:
Agar <fieldset disabled> diya ho to uske andar ke saare form controls disabled ho jaate hain.

Example:
<fieldset disabled>
  <input type="text" name="name">
</fieldset>

Use Cases:
✔ User input temporarily block karna.

99. HTML mein formaction attribute ka use kya hai?
Answer:
Submit button par use karke alag-alag buttons ke liye alag action URL set kar sakte hain.

Example:
<form method="POST">
  <button type="submit" formaction="/save">Save</button>
  <button type="submit" formaction="/submit">Submit</button>
</form>

Use Cases:
✔ Same form ke multiple actions handle karna.

100. <meta name="theme-color"> ka use kya hai?
Answer:
Mobile browser ke address bar ya UI ka color set karne ke liye use hota hai.

Example:
<meta name="theme-color" content="#0d6efd">

Use Cases:
✔ Branding aur aesthetic control.

101. <source> tag mein media attribute ka use kya hai?
Answer:
Responsive images ke liye media attribute use hota hai – alag screen size ke liye alag images load karne ke liye.

Example:
<picture>
  <source media="(max-width: 600px)" srcset="small.jpg">
  <source media="(min-width: 601px)" srcset="large.jpg">
  <img src="default.jpg" alt="Example">
</picture>

Use Cases:
✔ Performance aur responsiveness enhance karna.

102. <link rel="stylesheet"> aur <style> tag mein kya difference hai?

Answer:
✔ <link> external CSS file ko load karta hai.
✔ <style> page ke andar inline CSS define karta hai.

Use Cases:
✔ Modular aur maintainable styling.

103. HTML mein <template> tag ko crawl engines kaise treat karte hain?
Answer:
✔ Template content render nahi hota jab tak JavaScript se use na kiya jaye.
✔ SEO mein ye content ignore ho sakta hai agar proper fallback na diya ho.

104. <iframe> mein referrerpolicy="strict-origin" ka matlab kya hai?
Answer:
✔ Sirf origin (domain) send karega, path nahi.
✔ Sensitive URLs ko hide karne mein madad karta hai.

105. <meta charset="UTF-8"> na ho to kya problem ho sakti hai?
Answer:
✔ Special characters garbled ho jaayenge.
✔ Emojis, accented letters properly display nahi honge.





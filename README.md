
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Side Hustle Hub</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"/>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
}

:root{
--bg:#060816;
--card:#0d1324;
--accent:#00e5ff;
--text:#ffffff;
--muted:#9ca3af;
--glass:rgba(255,255,255,.06);
--border:rgba(255,255,255,.08);
}

html{
scroll-behavior:smooth;
}

body{
font-family:'Poppins',sans-serif;
background:var(--bg);
color:var(--text);
overflow-x:hidden;
}

/* HERO */

.hero{
min-height:100vh;
padding:80px 20px;
display:flex;
align-items:center;
justify-content:center;
text-align:center;
position:relative;
overflow:hidden;
}

.hero::before{
content:'';
position:absolute;
width:700px;
height:700px;
background:radial-gradient(circle,var(--accent),transparent 70%);
opacity:.15;
top:-250px;
right:-250px;
}

.hero-content{
max-width:900px;
position:relative;
z-index:2;
}

.hero h1{
font-size:3rem;
line-height:1.2;
margin-bottom:20px;
}

.hero p{
color:var(--muted);
line-height:1.9;
font-size:1.05rem;
}

.hero-buttons{
margin-top:35px;
display:flex;
justify-content:center;
gap:15px;
flex-wrap:wrap;
}

.hero-buttons a{
padding:14px 24px;
border-radius:50px;
text-decoration:none;
font-weight:600;
transition:.3s;
}

.btn-primary{
background:var(--accent);
color:#000;
}

.btn-secondary{
border:1px solid var(--border);
color:#fff;
background:var(--glass);
backdrop-filter:blur(10px);
}

.hero-buttons a:hover{
transform:translateY(-4px);
}

/* SLIDER */

.slider-wrap{
padding:40px 20px;
overflow:hidden;
}

.slider-title{
font-size:2rem;
margin-bottom:25px;
text-align:center;
}

.slider{
display:flex;
gap:20px;
animation:slide 35s linear infinite;
width:max-content;
}

.slide-card{
width:300px;
background:var(--card);
padding:25px;
border-radius:22px;
border:1px solid var(--border);
backdrop-filter:blur(10px);
flex-shrink:0;
}

.slide-card i{
font-size:35px;
color:var(--accent);
margin-bottom:20px;
}

.slide-card h3{
margin-bottom:12px;
}

.slide-card p{
color:var(--muted);
line-height:1.8;
font-size:.95rem;
}

@keyframes slide{
0%{
transform:translateX(0);
}
100%{
transform:translateX(-50%);
}
}

/* FAQ */

.faq-section{
padding:80px 20px;
max-width:1100px;
margin:auto;
}

.section-title{
font-size:2.1rem;
text-align:center;
margin-bottom:40px;
}

.faq-item{
margin-bottom:18px;
background:var(--card);
border-radius:20px;
overflow:hidden;
border:1px solid var(--border);
}

.faq-question{
padding:22px;
cursor:pointer;
display:flex;
justify-content:space-between;
align-items:center;
font-weight:600;
}

.faq-answer{
max-height:0;
overflow:hidden;
transition:max-height .4s ease;
}

.faq-answer-content{
padding:0 22px 22px;
color:var(--muted);
line-height:1.9;
}

/* GRID */

.tools-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
gap:20px;
padding:40px 20px 90px;
max-width:1200px;
margin:auto;
}

.tool-card{
background:var(--card);
padding:25px;
border-radius:22px;
border:1px solid var(--border);
transition:.4s;
}

.tool-card:hover{
transform:translateY(-6px);
border-color:var(--accent);
}

.tool-card i{
font-size:32px;
color:var(--accent);
margin-bottom:18px;
}

.tool-card h3{
margin-bottom:12px;
}

.tool-card p{
color:var(--muted);
line-height:1.8;
}

/* FLOATING BUTTON */

#launcher{
position:fixed;
bottom:25px;
right:25px;
width:52px;
height:52px;
border-radius:50%;
background:rgba(255,255,255,.08);
backdrop-filter:blur(15px);
border:1px solid var(--border);
display:flex;
align-items:center;
justify-content:center;
cursor:pointer;
z-index:99999;
box-shadow:0 0 30px rgba(0,0,0,.4);
transition:.4s;
}

#launcher:hover{
transform:scale(1.08);
border-color:var(--accent);
}

#launcher i{
font-size:22px;
color:var(--accent);
}

/* OVERLAY */

#overlay{
position:fixed;
inset:0;
background:rgba(0,0,0,.92);
backdrop-filter:blur(15px);
display:none;
flex-direction:column;
z-index:100000;
padding:20px;
}

.overlay-top{
display:flex;
justify-content:space-between;
align-items:center;
padding:0 5px 15px;
}

.overlay-top h3{
font-size:.9rem;
letter-spacing:2px;
color:var(--accent);
}

.close-btn{
background:none;
border:none;
color:#fff;
font-size:15px;
cursor:pointer;
}

.iframe-shell{
flex:1;
border-radius:25px;
overflow:hidden;
border:1px solid var(--border);
background:#fff;
}

.iframe-shell iframe{
width:100%;
height:120%;
border:none;
}

/* MENU PANEL */

.menu-panel{
position:fixed;
bottom:100px;
right:25px;
display:none;
flex-direction:column;
gap:12px;
z-index:99998;
}

.menu-panel button{
background:var(--card);
border:1px solid var(--border);
color:#fff;
padding:14px 18px;
border-radius:16px;
cursor:pointer;
display:flex;
align-items:center;
gap:10px;
transition:.3s;
backdrop-filter:blur(10px);
}

.menu-panel button:hover{
border-color:var(--accent);
transform:translateX(-5px);
}

/* FOOTER */

footer{
padding:40px 20px;
text-align:center;
color:var(--muted);
border-top:1px solid var(--border);
}

/* MOBILE */

@media(max-width:768px){

.hero h1{
font-size:2rem;
}

.slider-title,
.section-title{
font-size:1.5rem;
}

.slide-card{
width:260px;
}

}

</style>
</head>

<body>

<!-- HERO -->

<section class="hero">

<div class="hero-content">

<h1>
Build Smarter Side Hustles With AI & Automation
</h1>

<p>
Discover premium business tools, AI startup ideas, online income systems,
automation resources, affiliate tools, dropshipping platforms,
and modern productivity solutions designed for creators,
freelancers, startups, and online entrepreneurs.
</p>

<div class="hero-buttons">
<a href="#tools" class="btn-primary">
Browse Tools
</a>

<a href="#faq" class="btn-secondary">
Learn More
</a>
</div>

</div>

</section>

<!-- AUTO SLIDER -->

<section class="slider-wrap">

<h2 class="slider-title">
Trending AI Side Hustles
</h2>

<div class="slider">

<div class="slide-card">
<i class="fas fa-robot"></i>
<h3>AI Content Agency</h3>
<p>
Start an AI content writing business using automation tools for blogs,
social media, and businesses.
</p>
</div>

<div class="slide-card">
<i class="fas fa-store"></i>
<h3>AI Dropshipping</h3>
<p>
Build automated ecommerce stores with AI product descriptions,
customer support, and marketing.
</p>
</div>

<div class="slide-card">
<i class="fas fa-video"></i>
<h3>Faceless Video Channel</h3>
<p>
Create YouTube automation channels using AI voiceovers,
scripts, and video generators.
</p>
</div>

<div class="slide-card">
<i class="fas fa-chart-line"></i>
<h3>Affiliate Marketing</h3>
<p>
Promote digital tools, AI apps, and business products
through content and automation.
</p>
</div>

<div class="slide-card">
<i class="fas fa-laptop-code"></i>
<h3>AI Web Apps</h3>
<p>
Launch SaaS tools, AI chatbots,
and premium business solutions online.
</p>
</div>

<div class="slide-card">
<i class="fas fa-mobile-screen"></i>
<h3>Digital Products</h3>
<p>
Sell ebooks, templates, prompts,
and premium startup resources.
</p>
</div>

</div>

</section>

<!-- TOOLS -->

<section id="tools">

<h2 class="section-title">
Premium Business Tools
</h2>

<div class="tools-grid">

<div class="tool-card">
<i class="fas fa-cloud"></i>
<h3>Web Hosting</h3>
<p>
Fast hosting, domains, cloud deployment,
and startup infrastructure solutions.
</p>
</div>

<div class="tool-card">
<i class="fas fa-cart-shopping"></i>
<h3>Ecommerce</h3>
<p>
AI-powered stores, dropshipping systems,
and online selling tools.
</p>
</div>

<div class="tool-card">
<i class="fas fa-bullhorn"></i>
<h3>Marketing</h3>
<p>
SEO platforms, email marketing,
and social media automation.
</p>
</div>

<div class="tool-card">
<i class="fas fa-comments"></i>
<h3>Live Chat</h3>
<p>
Customer support widgets,
WhatsApp commerce, and AI chatbots.
</p>
</div>

<div class="tool-card">
<i class="fas fa-pen-ruler"></i>
<h3>Design Tools</h3>
<p>
Canva alternatives, AI graphics,
and branding systems.
</p>
</div>

<div class="tool-card">
<i class="fas fa-money-bill-trend-up"></i>
<h3>Monetisation</h3>
<p>
Affiliate systems, CPM networks,
and digital income tools.
</p>
</div>

</div>

</section>

<!-- FAQ -->

<section class="faq-section" id="faq">

<h2 class="section-title">
Frequently Asked Questions
</h2>

<div class="faq-item">

<div class="faq-question">
<span>What are AI side hustles?</span>
<span>+</span>
</div>

<div class="faq-answer">
<div class="faq-answer-content">

AI side hustles are online businesses powered by artificial intelligence,
automation, and digital tools. They include content creation,
affiliate marketing, ecommerce automation,
AI services, and digital products.

</div>
</div>

</div>

<div class="faq-item">

<div class="faq-question">
<span>Can beginners start?</span>
<span>+</span>
</div>

<div class="faq-answer">
<div class="faq-answer-content">

Yes. Most modern AI tools require little or no coding.
Beginners can build websites,
create content, automate tasks,
and launch online businesses using ready-made tools.

</div>
</div>

</div>

<div class="faq-item">

<div class="faq-question">
<span>What tools help startups grow?</span>
<span>+</span>
</div>

<div class="faq-answer">
<div class="faq-answer-content">

Popular startup tools include:
Notion, Canva, Trello, ChatGPT,
HubSpot, Shopify, Mailchimp,
and AI automation platforms.

</div>
</div>

</div>

</section>

<!-- FLOATING -->

<div id="launcher">
<i class="fas fa-layer-group"></i>
</div>

<div class="menu-panel" id="menuPanel">

<button onclick="openOverlay('https://debeatzgh1.github.io/Home-/')">
<i class="fas fa-house"></i>

</button>

<button onclick="openOverlay('https://paystack.shop/debeatzgh')">
<i class="fas fa-store"></i>

</button>

<button onclick="openOverlay('https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/')">
<i class="fas fa-blog"></i>

</button>

<button onclick="openOverlay('https://debeatzgh1.github.io/firebase-front-end-components/')">
<i class="fab fa-github"></i>

</button>

</div>

<!-- OVERLAY -->

<div id="overlay">

<div class="overlay-top">
<h3>LIVE html PREVIEWs </h3>

<button class="close-btn" onclick="closeOverlay()">
<i class="fas fa-times"></i>
</button>
</div>

<div class="iframe-shell">
<iframe id="frame"></iframe>
</div>

</div>

<footer>
© 2026 AI Side Hustle Hub • Premium GitHub Pages Interface
</footer>

<script>

/* FAQ */

document.querySelectorAll('.faq-question').forEach(btn=>{

btn.addEventListener('click',()=>{

const answer=btn.nextElementSibling;

if(answer.style.maxHeight){
answer.style.maxHeight=null;
btn.querySelector('span:last-child').innerHTML='+';
}else{
answer.style.maxHeight=answer.scrollHeight+'px';
btn.querySelector('span:last-child').innerHTML='−';
}

});

});

/* FLOAT MENU */

const launcher=document.getElementById('launcher');
const panel=document.getElementById('menuPanel');

launcher.onclick=()=>{

panel.style.display=
panel.style.display==='flex'
?'none'
:'flex';

};

/* OVERLAY */

function openOverlay(url){

document.getElementById('overlay').style.display='flex';

document.getElementById('frame').src=url;

document.body.style.overflow='hidden';

panel.style.display='none';

}

function closeOverlay(){

document.getElementById('overlay').style.display='none';

document.getElementById('frame').src='';

document.body.style.overflow='auto';

}

/* AUTO PULSE */

setInterval(()=>{

launcher.animate([
{transform:'scale(1)'},
{transform:'scale(1.12)'},
{transform:'scale(1)'}
],{
duration:1200
});

},5000);

</script>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --gh-bg: #0d1117;
            --gh-border: #30363d;
            --hustle-accent: #238636;
            --text-gray: #8b949e;
        }

        /* 1. Slim Top Overlay Banner */
        .mini-hustle-card {
            position: fixed;
            top: 10px; /* Positioned at the top */
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 450px; /* Narrower for a cleaner look */
            background: var(--gh-bg);
            border: 1px solid var(--gh-border);
            border-radius: 8px; /* Slightly sharper professional corners */
            padding: 10px 15px;
            cursor: pointer;
            box-shadow: 0 4px 20px rgba(0,0,0,0.6);
            z-index: 1000;
            overflow: hidden;
            display: flex;
            align-items: center;
            gap: 12px;
            animation: borderPulse 4s infinite;
        }

        @keyframes borderPulse {
            0% { border-color: var(--gh-border); }
            50% { border-color: var(--hustle-accent); box-shadow: 0 0 10px rgba(35, 134, 54, 0.2); }
            100% { border-color: var(--gh-border); }
        }

        /* 2. Compact Auto-Slide Content */
        .slide-container {
            flex-grow: 1;
        }

        .slide-text {
            display: none;
            font-size: 0.8rem; /* Smaller font for top overlay */
            line-height: 1.2;
            color: white;
            animation: fadeSlide 0.5s ease;
        }

        .slide-text.active { display: block; }

        @keyframes fadeSlide {
            from { opacity: 0; transform: translateY(-5px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hustle-tag {
            background: var(--hustle-accent);
            color: white;
            font-size: 0.65rem;
            font-weight: bold;
            padding: 2px 6px;
            border-radius: 4px;
            text-transform: uppercase;
            white-space: nowrap;
        }

        /* 3. Full-Screen Iframe Overlay */
        #iframe-overlay {
            position: fixed;
            top: 0; left: 0; 
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.9);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            backdrop-filter: blur(8px);
        }

        .iframe-container {
            width: 95%; /* Wider for GitHub Page tools */
            max-width: 1200px;
            height: 90vh;
            background: #ffffff;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 50px rgba(0,0,0,0.5);
        }

        .close-iframe {
            position: absolute;
            top: 10px;
            right: 15px;
            background: #f85149;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            z-index: 10001;
            font-weight: bold;
            font-size: 0.8rem;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>

    <div class="mini-hustle-card" onclick="openHustleKit()">
        <span class="hustle-tag">NEW</span>
        
        <div class="slide-container">
            <div class="slide-text active">
                <strong>Side Hustle Tools:</strong> Launch your digital business today.
            </div>
            
            <div class="slide-text">
                <strong>Entrepreneur Ideas:</strong> Thrive in the digital economy.
            </div>

            <div class="slide-text">
                <strong>One-Stop Place:</strong> Everything you need online.
            </div>
        </div>

        <span style="color: var(--text-gray); font-size: 1rem;">›</span>
    </div>

    <div id="iframe-overlay" onclick="closeHustleKit(event)">
        <div class="iframe-container" onclick="event.stopPropagation()">
            <button class="close-iframe" onclick="closeHustleKit(event)">CLOSE [X]</button>
            <iframe src="https://debeatzgh1.github.io/Side-hustle-starter-kit-/" title="Side Hustle Starter Kit"></iframe>
        </div>
    </div>

    <script>
        // Auto-Slide Logic
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide-text');
        
        function rotateSlides() {
            slides[currentSlide].classList.remove('active');
            currentSlide = (currentSlide + 1) % slides.length;
            slides[currentSlide].classList.add('active');
        }

        setInterval(rotateSlides, 3500); 

        // Iframe Open/Close Logic
        function openHustleKit() {
            document.getElementById('iframe-overlay').style.display = 'flex';
            document.body.style.overflow = 'hidden'; // Prevent background scroll
        }

        function closeHustleKit(event) {
            document.getElementById('iframe-overlay').style.display = 'none';
            document.body.style.overflow = 'auto'; // Restore scroll
        }
    </script>
</body>
</html>




<style>
  /* 🌟 Fade Slide Animation */
  @keyframes fadeSlideUp {
    0% { opacity: 0; transform: translateX(-50%) translateY(20px); }
    100% { opacity: 1; transform: translateX(-50%) translateY(0); }
  }

  /* ❤️ Heartbeat Animation */
  @keyframes heartbeat {
    0% { transform: translateX(-50%) scale(1); }
    25% { transform: translateX(-50%) scale(1.08); }
    50% { transform: translateX(-50%) scale(1); }
    75% { transform: translateX(-50%) scale(1.08); }
    100% { transform: translateX(-50%) scale(1); }
  }

  .floating-btn-group {
    animation: fadeSlideUp 0.6s ease-out;
  }

  /* Iframe Modal Styles */
  #iframe-modal {
    display: none;
    position: fixed;
    z-index: 9999;
    left: 0;
    top: 0;
    width: 100%;
    height: 115%;
    background: rgba(0,0,0,0.6);
    backdrop-filter: blur(4px);
  }

  .modal-content {
    position: relative;
    margin: 2% auto;
    background: #fff;
    border-radius: 16px;
    width: 95%;
    height: 90%;
    box-shadow: 0 8px 24px rgba(0,0,0,0.3);
    overflow: hidden;
    animation: fadeIn 0.3s ease;
  }

  #modal-iframe {
    width: 100%;
    height: 105%;
    border: none;
  }

  .close-btn {
    position: absolute;
    top: 10px;
    right: 18px;
    font-size: 30px;
    color: #333;
    cursor: pointer;
    transition: color 0.2s;
    z-index: 10;
  }

  .close-btn:hover {
    color: #e11d48;
  }

  @keyframes fadeIn {
    from {opacity: 0; transform: translateY(-10px);}
    to {opacity: 1; transform: translateY(0);}
  }
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {

  // 🔹 Floating Button Group
  const btnGroup = document.createElement("div");
  btnGroup.className = "floating-btn-group";
  Object.assign(btnGroup.style, {
    position: "fixed",
    bottom: "18px",
    left: "50%",
    transform: "translateX(-50%)",
    zIndex: "9999",
    display: "flex",
    gap: "12px",
    animation: "heartbeat 2.5s infinite ease-in-out, fadeSlideUp 0.6s ease-out forwards"
  });

  // 🔹 Buttons (only TWO)
  const buttons = [
    {
      text: "📌 Blog",
      bg: "#16a34a",
      url: "https://digimartgh.blogspot.com/"
    },
    {
      text: "💡 Ideas",
      bg: "#c026d3",
      url: "https://msha.ke/debeatzgh"
    }
  ];

  // 🔹 Modal
  const modal = document.createElement("div");
  modal.id = "iframe-modal";
  modal.innerHTML = `
    <div class="modal-content">
      <span class="close-btn">&times;</span>
      <iframe id="modal-iframe" src="" loading="lazy"></iframe>
    </div>
  `;
  document.body.appendChild(modal);

  // 🔹 Add Buttons
  buttons.forEach(btn => {
    const a = document.createElement("a");
    a.href = "#";
    a.innerText = btn.text;

    Object.assign(a.style, {
      background: btn.bg,
      color: "#fff",
      padding: "12px 20px",
      borderRadius: "30px",
      textDecoration: "none",
      fontSize: "14px",
      fontWeight: "700",
      whiteSpace: "nowrap",
      boxShadow: "0 4px 10px rgba(0,0,0,0.25)"
    });

    a.addEventListener("click", function (e) {
      e.preventDefault();
      document.getElementById("modal-iframe").src = btn.url;
      document.getElementById("iframe-modal").style.display = "block";
    });

    btnGroup.appendChild(a);
  });

  document.body.appendChild(btnGroup);

  // 🔹 Close Modal
  document.addEventListener("click", function (e) {
    if (e.target.classList.contains("close-btn") || e.target.id === "iframe-modal") {
      modal.style.display = "none";
      document.getElementById("modal-iframe").src = "";
    }
  });

  // 🔹 Handle external ads
  document.getElementById("modal-iframe").addEventListener("load", function () {
    try {
      const links = this.contentDocument.querySelectorAll("a");
      links.forEach(link => {
        if (!link.href.includes("debeatzgh.wordpress.com")) {
          link.setAttribute("target", "_blank");
          link.setAttribute("rel", "noopener");
        }
      });
    } catch (err) {
      console.warn("External site - cannot rewrite links");
    }
  });

});
</script>

<!-- Elfsight Button | Untitled Button -->
<script src="https://elfsightcdn.com/platform.js" async></script>
<div class="elfsight-app-a33a4ccd-0457-4a6c-a256-aa3855b0977d" data-elfsight-app-lazy></div>

A Curated Framework for High-ROI Income Streams & Automation Tools

## 💎 Why a Side Hustle in 2026?
The traditional "9-to-5" is no longer the only path to stability. In 2026, the most successful individuals treat their skills as a portfolio. Whether you are looking for "Beer Money" ($200/mo) or "Life-Changing Income" ($10k+/mo), this kit provides the blueprint.

## 🚀 Top Side Hustle Categories (2026 Trends)
1. AI Content Support & "Vibe" Optimization
The Idea: Businesses are drowning in generic AI content. They need humans to "humanize" the output, fact-check, and optimize prompts.
Skill Level: Medium (Requires familiarity with LLMs like GPT-5 and Claude 3).
Potential: $40–$100/hour.
Tags: #AI #Freelance #FutureOfWork
2. UGC (User Generated Content) Video Creator
The Idea: Brands no longer want polished ads; they want "real" people filming product reviews on their phones for TikTok, Reels, and Shorts.
Skill Level: Low (Confidence on camera is key).
Potential: $150–$500 per 30-second video.
Tags: #UGC #Marketing #CreatorEconomy
3. Fractional Administrative Support (Virtual Assistant 2.0)
The Idea: Moving beyond data entry. Modern VAs manage AI agents, handle complex scheduling, and manage specialized software like HubSpot or Notion.
Skill Level: High (Requires organizational mastery).
Potential: $30–$60/hour.
Tags: #RemoteWork #Organization #Efficiency
4. Digital Micro-Assets (Templates & Tools)
The Idea: Building and selling specialized Notion templates, Excel budgeters, or Figma UI kits.
Skill Level: Medium (Design or logic skills needed).
Potential: Passive Income ($500–$5k/month).
Tags: #PassiveIncome #DigitalProducts #Notion

## 🔧 The 2026 Tech Stack (Essential Tools)
Category
Recommended Tool
Why You Need It
Automation
Zapier / Make
Connects your apps so you can "work" while you sleep.
Content
Claude / Jasper
For drafting high-quality, long-form professional copy.
Video
CapCut / Descript
Auto-captions and simple AI-powered video editing.
Organization
Notion / ClickUp
To manage your clients, tasks, and "Side Hustle CRM."
Payments
Stripe / Gumroad
Instant "Buy Now" links to collect global payments.
Research
Perplexity AI
For real-time market research and source-backed data.


## 📈 The Step-by-Step Launch Framework
Step 1: The "2-Hour" Audit
Don't start with what you want to do; start with what people will pay for.
List 3 things people always ask you for help with.
Check Upwork or Fiverr to see the going rate for those skills.
Step 2: Build Your "Minimum Viable Presence"
In 2026, you don't need a massive website. You need:
A clean LinkedIn profile optimized with keywords.
A Stripe Payment Link or a simple Carrd landing page.
A "Portfolio of One" (One high-quality sample of your work).
Step 3: The Outreach Engine
Stop waiting for clients. Use the 10-5-1 Method:
10 Cold DMs/Emails per day.
5 Helpful comments on industry leaders' posts.
1 Value-driven post on your own profile.


# 💬 Community Discussion 
What is holding you back from starting?
Is it a lack of a clear idea?
Is it the technical setup?
Is it fear of the "first sell"?




# 📅 The 30-Day "First Dollar" Sprint
A daily roadmap to launching your side hustle in 2026.

## 🟦 Week 1: Foundation & Market Fit
Goal: Identify a high-ROI skill and prove people will pay for it.
Day
Task
Description
01
The Skill Audit
List your top 3 skills. Cross-reference them with 2026 trends (AI, UGC, fractional support).
02
Niche Selection
Choose one specific audience (e.g., "AI prompting for Real Estate Agents").
03
Competitor Spy
Search Upwork/Fiverr. What are others charging? What is their "bad" review (solve that).
04
The "Only" Statement
Write your unique value prop: "I am the only [Hustle] that helps [Audience] do [Result]."
05
The Smoke Test
Post the "Problem Interview" script (from Module 2) on Reddit or LinkedIn.
06
Review Feedback
Analyze comments. Did people care? If no, pivot the niche. If yes, move to Day 7.
07
Rest & Strategy
Review your "Market Fit." Clear your head for the Build Phase.


## 🟧 Week 2: Infrastructure (The "Lean" Build)
Goal: Set up your digital storefront without spending a dime.
Day
Task
Description
08
Brand Identity
Spend 1 hour on Canva. Create a logo and a 3-color palette. Keep it simple.
09
Landing Page
Build a 1-page site on Carrd or a Notion page. Focus on the offer, not the design.
10
Payment Setup
Create a Stripe or PayPal business account. Generate one "Pay Now" link.
11
The Lead Magnet
Create a free PDF or 2-min video that proves you know what you’re doing.
12
Automation Setup
Link your landing page to an email list using Mailchimp or Zapier.
13
Portfolio Piece
Create one "Mock Project." Show exactly what the customer will get.
14
System Audit
Click every button on your site. Ensure the payment link works.


## 🟩 Week 3: Market Infiltration
Goal: Get your first 100 sets of eyes on your offer.
Day
Task
Description
15
Social Optimization
Update your LinkedIn/Twitter bio to reflect your new hustle. Add your link.
16
The "Warm" Reach
DM 10 people you know. Ask for feedback, not a sale.
17
Cold Outreach (A)
Find 10 potential clients. Send the "Quick Question" script from the Kit.
18
Content Pillar 1
Post a "How-To" guide related to your hustle on your main social feed.
19
Cold Outreach (B)
Follow up with Day 17 leads. Send 10 more new DMs.
20
Community Value
Answer 5 questions in a niche Facebook Group or Subreddit. Don't link yet.
21
Refine Pitch
Based on DM responses, tweak your pricing or your "Only" statement.


## 🟥 Week 4: The Sales Push & Delivery
Goal: Close your first client and establish a workflow.
Day
Task
Description
22
The "Founding Member"
Post a limited-time offer: "50% off for the first 3 clients in exchange for a testimonial."
23
Active Selling
Double outreach. Send 20 DMs/Emails today.
24
The Follow-Up
Reach out to everyone who "liked" your posts this week. Ask if they need help.
25
Onboarding Prep
Create a "Welcome" doc. What happens after they pay? (A simple Google Doc is fine).
26
The "Hard" Ask
Direct pitch to your hottest 3 leads. Ask for the business.
27
Content Pillar 2
Post a "Why I started this" story. Vulnerability drives sales.
28
First Delivery
(Hopefully) Work on your first paid task. Focus on over-delivering.
29
Testimonial Hunt
Ask your first client (or beta testers) for a 2-sentence review.
30
The Month-Ahead
Calculate ROI. How many hours did you spend? How much did you make? Scale up.


## 💡 Success Tips for 2026
Morning Momentum: Spend your first 30 minutes of the day on Day-specific tasks before opening your "9-to-5" email.
Batch Content: On Day 18 and 27, write 5 extra posts so you have a "bank" for next month.
The $0 Rule: Don't buy "Premium" versions of tools until the side hustle has paid for them.

On Day 25, your goal is to transition from "Salesperson" to "Professional Partner." Providing a Welcome Doc (also called a Welcome Packet) eliminates client anxiety, sets firm boundaries, and makes you look like a high-end agency—even if you're a solopreneur.
Copy and paste the template below into a Google Doc or Notion Page.

## 📄  Client Welcome & Onboarding Guide
Welcome to the Project!
Hi [Client Name], I’m thrilled to be working with you on [Project Name]. This document contains everything you need to know about how we will communicate, how the work gets done, and what to expect over the coming weeks.

## 🚀 1. The Project Roadmap
Here is the path we’re taking to get to your final result.
Phase 1: Kickoff & Discovery – [Date/Deadline]
Phase 2: First Draft / Prototype – [Date/Deadline]
Phase 3: Revisions & Feedback – [Date/Deadline]
Phase 4: Final Delivery & Handoff – [Date/Deadline]

## 💬 2. Communication Guidelines
To keep the project moving efficiently, let’s stick to these "Rules of the Road."
Primary Channel: All project-related communication should happen via [Email/Slack/Notion]. (This ensures nothing gets lost in social media DMs).
Office Hours: I am available [Monday–Friday, 9 AM – 5 PM Your Timezone].
Response Time: You can expect a response within [24–48 hours] during business days.
Urgent Matters: If there is a true emergency, please prefix your email subject with [URGENT].

## 🛠️ 3. Tools We Will Use
Please ensure you have access to these tools so we can collaborate smoothly.
[Tool 1, e.g., Google Drive]: Where I will store all final deliverables.
[Tool 2, e.g., Figma/Loom]: Where I will share progress videos or design drafts.
[Tool 3, e.g., Stripe]: For all invoicing and financial transactions.

## 📋 4. What I Need From You (Action Items)
Before we can officially start Phase 1, please complete the following:
[ ] Sign the Contract: [Link to Digital Signature]
[ ] Complete the Intake Form: [Link to Google Form/Notion]
[ ] Provide Assets: Please upload your logo, brand colors, or login credentials to this folder: [Link].
[ ] Deposit: Confirm payment of the 50% kickoff invoice.

## ⚖️ 5. Boundaries & Expectations
Revisions: This project includes [Number, e.g., 2] rounds of revisions. Additional rounds will be billed at $[Your Rate]/hour.
Scope Creep: If we decide to add new features or tasks not mentioned in our original agreement, I will provide a separate "Add-on" quote before starting.
Feedback: To stay on schedule, please provide feedback on drafts within [3 business days].

## ❓ 6. Frequently Asked Questions
Q: Can we hop on a quick unscheduled call?
A: To protect "Deep Work" time for your project, all calls must be scheduled 24 hours in advance via my [Calendly Link].
Q: What if I’m not happy with the first draft?
A: Don't worry! That's what the revision phase is for. We will use your feedback to pivot and refine until it meets the project goals.

Next Step:
Please reply to the welcome email with "Let's Go!" once you have reviewed this document and completed the checkboxes in Section 4.
I can't wait to get started!

Pro-Tip for Day 25:
When you send this to your client, send it as a PDF or a Read-only Notion link. It makes the "Rules of the Road" feel official and reduces the chance of them trying to negotiate your boundaries later!




<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Debeatzgh Multi-Tab Launcher</title>

<link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.4.1/dist/tailwind.min.css" rel="stylesheet">

<style>
/* ===== MODAL ===== */
.modal-bg{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.7);
  backdrop-filter:blur(6px);
  z-index:9999;
}
.modal-box{
  width:96%;
  height:94%;
  background:#fff;
  border-radius:18px;
  overflow:hidden;
  display:flex;
  flex-direction:column;
}

/* ===== TABS ===== */
.tabs{
  display:flex;
  gap:6px;
  padding:10px;
  background:#0f172a;
}
.tab{
  padding:8px 14px;
  border-radius:10px;
  font-size:13px;
  font-weight:700;
  color:#cbd5f5;
  cursor:pointer;
}
.tab.active{
  background:#2563eb;
  color:#fff;
}

/* ===== CONTROLS ===== */
.controls{
  display:flex;
  gap:8px;
  padding:8px 10px;
  background:#020617;
}
.ctrl-btn{
  background:rgba(255,255,255,.15);
  color:#fff;
  padding:6px 12px;
  border-radius:8px;
  font-size:12px;
  font-weight:700;
  cursor:pointer;
}

/* ===== IFRAME ===== */
iframe{
  flex:1;
  width:100%;
  border:none;
}
</style>
</head>

<body class="bg-gray-100">

<header class="text-center py-10">
  <h1 class="text-3xl font-bold">AI & Knowledge Hub</h1>
  <p class="text-gray-600 mt-2 max-w-xl mx-auto">
    Access WordPress, Blogger, and Forms in one focused workspace.
  </p>
</header>

<!-- LAUNCHER CARDS -->
<div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-6 px-6">

  <div class="bg-white rounded-xl shadow p-6">
    <h3 class="text-xl font-bold mb-2">Build With AI</h3>
    <p class="text-sm text-gray-600 mb-4">
      WordPress AI deep-dives & guides
    </p>
    <button onclick="openLauncher('wordpress')"
      class="w-full bg-blue-600 text-white py-3 rounded-xl font-bold">
      Open WordPress
    </button>
  </div>

  <div class="bg-white rounded-xl shadow p-6">
    <h3 class="text-xl font-bold mb-2">AI Knowledge Blog</h3>
    <p class="text-sm text-gray-600 mb-4">
      Beginner-friendly Blogger content
    </p>
    <button onclick="openLauncher('blogger')"
      class="w-full bg-emerald-600 text-white py-3 rounded-xl font-bold">
      Open Blogger
    </button>
  </div>

</div>

<!-- MODAL -->
<div class="modal-bg" id="modal">
  <div class="modal-box" id="modalBox">

    <!-- TABS -->
    <div class="tabs">
      <div class="tab active" data-tab="wordpress">WordPress</div>
      <div class="tab" data-tab="blogger">Blogger</div>
      <div class="tab" data-tab="signin">Sign In</div>
      <div class="tab" data-tab="about">About</div>
    </div>

    <!-- CONTROLS -->
    <div class="controls">
      <div class="ctrl-btn" onclick="goBack()">⟵ Back</div>
      <div class="ctrl-btn" onclick="goForward()">⟶ Forward</div>
      <div class="ctrl-btn" onclick="toggleFS()">⛶ Fullscreen</div>
      <div class="ctrl-btn" onclick="closeLauncher()">✕ Close</div>
    </div>

    <!-- IFRAME -->
    <iframe id="frame"></iframe>

  </div>
</div>

<script>
const modal = document.getElementById("modal");
const frame = document.getElementById("frame");
const tabs = document.querySelectorAll(".tab");

/* ===== URL MAP ===== */
const URLS = {
  wordpress: "https://debeatzgh.wordpress.com/begin-a-side-hustle/",
  blogger: "https://debeatzgh1.github.io/Digital-Creator-s-Essential-Guides-Tools/",
  signin: "https://docs.google.com/forms/d/e/1FAIpQLSdXCPUz1JBq0W8MHN9VOE0p6cnp5Wtr74Ox2gqLLyzKi0UwKA/viewform",
  about: "https://form.jotform.com/241335470278053"
};

/* ===== HISTORY ===== */
let historyStack = [];
let historyIndex = -1;

function load(url){
  frame.src = url;
  if(historyStack[historyIndex] !== url){
    historyStack = historyStack.slice(0, historyIndex + 1);
    historyStack.push(url);
    historyIndex++;
  }
}

/* ===== OPEN LAUNCHER ===== */
function openLauncher(tab){
  modal.style.display = "flex";
  switchTab(tab);
}

/* ===== CLOSE ===== */
function closeLauncher(){
  modal.style.display = "none";
  frame.src = "";
  historyStack = [];
  historyIndex = -1;
  if(document.fullscreenElement) document.exitFullscreen();
}

/* ===== TAB SWITCHING ===== */
tabs.forEach(tabEl => {
  tabEl.addEventListener("click", () => {
    switchTab(tabEl.dataset.tab);
  });
});

function switchTab(tab){
  tabs.forEach(t => t.classList.remove("active"));
  document.querySelector(`.tab[data-tab="${tab}"]`).classList.add("active");
  load(URLS[tab]);
}

/* ===== NAVIGATION ===== */
function goBack(){
  if(historyIndex > 0){
    historyIndex--;
    frame.src = historyStack[historyIndex];
  }
}
function goForward(){
  if(historyIndex < historyStack.length - 1){
    historyIndex++;
    frame.src = historyStack[historyIndex];
  }
}

/* ===== FULLSCREEN ===== */
function toggleFS(){
  const el = document.getElementById("modalBox");
  if(!document.fullscreenElement) el.requestFullscreen();
  else document.exitFullscreen();
}
</script>

</body>
</html>

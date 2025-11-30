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

# 🚀 DigimartGH Side Hustle Tools & Startup Guides

Unlock your entrepreneurial journey with curated resources, actionable guides, trending updates, and practical tools for launching and growing side hustles or digital startups. Discover ideas, get inspired, and access everything you need—all in one welcoming space!

---

## 🌟 Explore the Hub

<table>
  <tr>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550752905574451607135626005441.jpg" width="110" style="border-radius:10px"/>
      <br><b>Home</b>
      <br><small>Start here to unlock all side hustle and startup resources. Sign in for personalized tools and updates.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/sign-in-for-more_19.html" style="background:#2b7cff;color:#fff;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">Go to Home</a>
    </td>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550752768858270075844257043940.jpg" width="110" style="border-radius:10px"/>
      <br><b>Side Hustle Updates</b>
      <br><small>Current trends, opportunities, and fresh updates to optimize and monetize your side hustle online.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/provided-by-httpsmsha.html" style="background:#0984e3;color:#fff;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">Read Updates</a>
    </td>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550417028037724303471824316179.jpg" width="110" style="border-radius:10px"/>
      <br><b>Side Hustle Tools</b>
      <br><small>Essential tools for launching and managing your online business—great for beginners and pros alike.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/how-to-start-online-business.html" style="background:#fdcb6e;color:#222;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">Explore Tools</a>
    </td>
  </tr>
  <tr>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg" width="110" style="border-radius:10px"/>
      <br><b>Side Hustle Ideas</b>
      <br><small>Get inspiration and unlock new side hustle ideas. Learn how to protect your digital ventures and data privacy.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/data-and-privacy.html" style="background:#6c5ce7;color:#fff;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">See Ideas</a>
    </td>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550753355015215823208011315422.jpg" width="110" style="border-radius:10px"/>
      <br><b>AI Side Hustle You Can Start</b>
      <br><small>Five proven AI side hustles you can launch today, complete with step-by-step guides and resources.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/five-proven-ai-side-hustle-you-can.html" style="background:#00b894;color:#fff;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">Start With AI</a>
    </td>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550417188267308669484942620808.jpg" width="110" style="border-radius:10><small>Learn about DigimartGH’s mission to empower digital hustlers, with practical insights for every step.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/about-us.html" style="background:#fab1a0;color:#222;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">About Us</a>
    </td>
  </tr>
  <tr>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550753129553143934409952739598.jpg" width="110" style="border-radius:10px"/>
      <br><b>Ultimate Guide to Side Hustle</b>
      <br><small>Comprehensive strategies and models for launching, managing, and scaling your side hustle successfully.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/about-online-business.html" style="background:#ff7675;color:#222;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">Ultimate Guide</a>
    </td>
    <td align="center" width="33%">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designamodernminimalisticlogoforadigitaltoolcalledall-in-onefloatinginfomenuforblogger5444122951694103302.jpg" width="110" style="border-radius:10px"/>
      <br><b>Ultimate Startup Guide</b>
      <br><small>DigimartGH’s startup store guide offers strategies, resources, and insights for building your own digital brand from scratch.</small>
      <br>
      <a href="https://digimartgh.blogspot.com/p/digimartgh-store.html" style="background:#00cec9;color:#222;border-radius:6px;padding:9px 22px;font-size:.97em;text-decoration:none;display:inline-block;margin-top:7px;font-weight:600;">Start Your Startup</a>
    </td>
  </tr>
</table>

---

## 💡 How To Use

- **Click** on colored buttons to instantly open guides (in same tab for best focus).
- **Preview each resource** with its professional thumbnail and concise description.
- **Find your topic fast** with clear titles and section organization.
- Perfect for browsing on both desktop and mobile!

---

**Created by [debeatzgh1](https://github.com/debeatzgh1) — Empowering your digital hustle, side projects, and startup dreams.**

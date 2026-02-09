<html lang="en">
<head>
<meta charset="UTF-8">
<title>EA Help Center Demo</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
html, body {
  margin:0;
  padding:0;
  font-family: Arial, Helvetica, sans-serif;
  background:#0b0f19;
  color:#e5e7eb;
}

/* ===== FULL WIDTH HEADER / FOOTER IMAGES ===== */
.header-banner,
.footer-banner {
  width:100vw;
  max-width:100vw;
  margin:0;
  padding:0;
  display:block;
}

/* ===== NAV ===== */
header {
  background:#111827;
  padding:18px 40px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  border-bottom:1px solid #1f2937;
}

.logo-wrap {
  display:flex;
  align-items:center;
  gap:12px;
}

.logo-wrap img {
  height:36px;
}

.logo-text {
  font-weight:700;
  font-size:20px;
  color:#f9fafb;
}

.header-search input {
  padding:10px 14px;
  border-radius:10px;
  border:1px solid #374151;
  width:280px;
  background:#0b1220;
  color:white;
}

.signin-btn {
  background:#3b82f6;
  border:none;
  color:white;
  padding:10px 16px;
  border-radius:10px;
  font-weight:600;
  cursor:pointer;
}

/* ===== HERO ===== */
.hero {
  background:#111827;
  text-align:center;
  padding:80px 20px;
}

.hero-search input {
  width:600px;
  max-width:95%;
  padding:18px;
  border-radius:14px;
  border:1px solid #374151;
  background:#020617;
  color:white;
}

/* ===== SECTIONS ===== */
.section {
  padding:60px 6%;
}

.grid {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
  gap:24px;
}

.card {
  background:#111827;
  border-radius:16px;
  padding:28px;
  border:1px solid #1f2937;
  transition:.25s;
}

.card:hover {
  transform:translateY(-6px);
  box-shadow:0 12px 28px rgba(0,0,0,0.6);
  border-color:#2563eb;
}

/* ===== IMAGE GRID ===== */
.image-grid {
  display:grid;
  grid-template-columns:repeat(3, 1fr);
  gap:16px;
  margin-top:30px;
}

.img-wrap {
  overflow:hidden;
  border-radius:16px;
  background:#020617;
}

.img-wrap img {
  width:100%;
  height:auto;
  display:block;
  transition: transform .45s ease;
}

.img-wrap:hover img {
  transform: scale(1.15);
}

/* ===== ARTICLES ===== */
.article {
  background:#111827;
  border-radius:14px;
  padding:20px;
  border:1px solid #1f2937;
  margin-bottom:14px;
}

.tag {
  display:inline-block;
  background:#1f2937;
  color:#93c5fd;
  padding:4px 10px;
  border-radius:10px;
  font-size:12px;
  margin-top:8px;
}

/* ===== AI AGENT SECTION ===== */
.agent-box {
  background:#111827;
  border:1px solid #1f2937;
  border-radius:20px;
  padding:40px;
  text-align:center;
}

.agent-box img {
  width:160px;
  margin-bottom:20px;
}

.primary { background:#2563eb; color:white; padding:14px 22px; border-radius:12px; border:none; }

/* ===== FOOTER ===== */
footer {
  text-align:center;
  padding:30px;
  background:#020617;
  color:#9ca3af;
}
</style>
</head>

<body>

<!-- HEADER IMAGE -->
<img src="header.png" class="header-banner">

<header>
  <div class="logo-wrap">
    <img src="EA.svg">
    <div class="logo-text">Help Center</div>
  </div>

  <div class="header-search">
    <input placeholder="Search help articles">
  </div>

  <button class="signin-btn">Sign In</button>
</header>

<section class="hero">
  <h1>How can we help?</h1>
  <div class="hero-search">
    <input id="searchBox" placeholder="Search topics, errors, features">
  </div>
</section>

<div class="section">
<h2>Browse Categories</h2>
<div class="grid">
  <div class="card">Account & Login</div>
  <div class="card">Payments</div>
  <div class="card">Integrations</div>
  <div class="card">Developer APIs</div>
</div>
</div>

<div class="section">
<h2>Feature Gallery</h2>
<div class="image-grid">
  <div class="img-wrap"><img src="1.jpg"></div>
  <div class="img-wrap"><img src="2.png"></div>
  <div class="img-wrap"><img src="3.jpg"></div>
  <div class="img-wrap"><img src="4.jpg"></div>
  <div class="img-wrap"><img src="5.jpg"></div>
  <div class="img-wrap"><img src="6.jpg"></div>
  <div class="img-wrap"><img src="7.jpg"></div>
  <div class="img-wrap"><img src="8.jpg"></div>
  <div class="img-wrap"><img src="9.jpg"></div>
</div>
</div>

<div class="section">
<h2>Popular Articles</h2>
<div id="articles"></div>
</div>

<!-- ===== AI AGENT / MESSAGING SECTION ===== -->
<div class="section">
  <div class="agent-box">
    <img src="helpotron.png">
    <h2>Meet Helpotron 🤖</h2>
    <p>Your in-game style support AI. Ask anything or start a live support chat.</p>
    <button class="primary">Launch Support Chat</button>
  </div>
</div>

<!-- FOOTER IMAGE -->
<img src="footer.png" class="footer-banner">

<footer>
Demo Help Center UI — Dark Theme
</footer>

<!-- PAGE SCRIPT -->
<script>
const articles = [
 {title:"Reset your password", tag:"Account"},
 {title:"Login verification issues", tag:"Account"},
 {title:"Configure payment gateway", tag:"Payments"},
 {title:"Integration setup steps", tag:"Integrations"},
 {title:"API authentication flow", tag:"Developer"}
];

function render(list){
 document.getElementById("articles").innerHTML =
  list.map(a => `
    <div class="article">
      <strong>${a.title}</strong>
      <div class="tag">${a.tag}</div>
    </div>
  `).join("");
}
render(articles);
</script>

<!-- ===== SALESFORCE EMBEDDED MESSAGING ===== -->
<script type='text/javascript'>
function initEmbeddedMessaging() {
	try {
		embeddedservice_bootstrap.settings.language = 'en_US';
		embeddedservice_bootstrap.init(
			'00Dfj00000GhufN',
			'Github_Messaging_Setting',
			'https://orgfarm-23fcbe497c-dev-ed.develop.my.site.com/ESWGithubMessagingSetti1768249695612',
			{ scrt2URL: 'https://orgfarm-23fcbe497c-dev-ed.develop.my.salesforce-scrt.com' }
		);
	} catch (err) {
		console.error('Error loading Embedded Messaging: ', err);
	}
};
</script>

<script src='https://orgfarm-23fcbe497c-dev-ed.develop.my.site.com/ESWGithubMessagingSetti1768249695612/assets/js/bootstrap.min.js'
onload='initEmbeddedMessaging()'></script>

</body>
</html>

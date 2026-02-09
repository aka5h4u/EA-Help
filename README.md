<html lang="en">
<head>
<meta charset="UTF-8">
<title>Help Center Demo</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  font-family: Arial, Helvetica, sans-serif;
  background:#f3f4f6;
  color:#111827;
}

/* ===== HEADER & FOOTER FULL WIDTH ===== */
.header-banner,
.footer-banner {
  width: 100vw;
  max-width: 100vw;
  height: 240px;
  object-fit: cover;
  display: block;
}

/* ===== NAV ===== */
header {
  background:#0f172a;
  color:white;
  padding:16px 28px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.logo { font-weight:700; font-size:18px; }

.header-search input {
  padding:10px;
  border-radius:8px;
  border:none;
  width:260px;
}

.signin-btn {
  background:#2563eb;
  border:none;
  color:white;
  padding:10px 16px;
  border-radius:8px;
  font-weight:600;
  cursor:pointer;
}

/* ===== HERO ===== */
.hero {
  background:#1f2937;
  color:white;
  text-align:center;
  padding:70px 20px;
}

.hero-search input {
  width:560px;
  max-width:92%;
  padding:16px;
  border-radius:14px;
  border:none;
  font-size:16px;
  margin-top:20px;
}

/* ===== CONTENT ===== */
.container {
  max-width:1100px;
  margin:auto;
  padding:50px 20px;
}

.grid {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:20px;
  margin-top:20px;
}

.card {
  background:white;
  border-radius:14px;
  padding:26px;
  border:1px solid #e5e7eb;
  transition:.25s;
}

.card:hover {
  transform:translateY(-5px);
  box-shadow:0 10px 24px rgba(0,0,0,0.08);
}

/* ===== IMAGE BLOCK — ORIGINAL SIZE ===== */
.image-grid {
  display:grid;
  grid-template-columns:repeat(3, 1fr);
  gap:14px;
  margin-top:40px;
}

.img-wrap {
  overflow:hidden;
  border-radius:14px;
  background:white;
}

.img-wrap img {
  width:100%;       /* fit column width */
  height:auto;      /* keep original ratio */
  display:block;
  transition: transform .45s ease;
}

.img-wrap:hover img {
  transform: scale(1.15);
}

/* ===== ARTICLES ===== */
.article {
  background:white;
  border-radius:12px;
  padding:18px;
  margin-bottom:14px;
  border:1px solid #e5e7eb;
}

.tag {
  display:inline-block;
  background:#e5e7eb;
  padding:4px 8px;
  border-radius:8px;
  font-size:12px;
  margin-top:8px;
}

/* ===== SUPPORT ===== */
.support {
  background:#e0e7ff;
  border-radius:16px;
  padding:40px;
  text-align:center;
  margin-top:40px;
}

button {
  padding:12px 18px;
  border-radius:10px;
  border:none;
  font-weight:700;
  cursor:pointer;
  margin:8px;
}

.primary { background:#2563eb; color:white; }
.outline { background:white; border:2px solid #2563eb; color:#2563eb; }

/* ===== FOOTER ===== */
footer {
  background:#0f172a;
  color:#cbd5f1;
  text-align:center;
  padding:26px;
}
</style>
</head>

<body>

<!-- TOP STATIC HEADER IMAGE -->
<img src="header.png" class="header-banner">

<header>
  <div class="logo">Help Center Demo</div>
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

<div class="container">

<h2>Browse Categories</h2>

<div class="grid">
  <div class="card">Account & Login</div>
  <div class="card">Payments</div>
  <div class="card">Integrations</div>
  <div class="card">Developer APIs</div>
</div>

<h2 style="margin-top:50px;">Feature Gallery</h2>

<div class="image-grid">
  <div class="img-wrap"><img src="1.jpg"></div>
  <div class="img-wrap"><img src="2.jpg"></div>
  <div class="img-wrap"><img src="3.jpg"></div>
  <div class="img-wrap"><img src="4.jpg"></div>
  <div class="img-wrap"><img src="5.jpg"></div>
  <div class="img-wrap"><img src="6.jpg"></div>
  <div class="img-wrap"><img src="7.jpg"></div>
  <div class="img-wrap"><img src="8.jpg"></div>
  <div class="img-wrap"><img src="9.jpg"></div>
</div>

<h2 style="margin-top:50px;">Popular Articles</h2>
<div id="articles"></div>

<div class="support">
  <h3>Still need help?</h3>
  <button class="primary">Open Case</button>
  <button class="outline">Start Chat</button>
</div>

</div>

<!-- BOTTOM STATIC FOOTER IMAGE -->
<img src="footer.png" class="footer-banner">

<footer>
Demo Help Center UI — Built for Feature Demonstrations
</footer>

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

document.getElementById("searchBox").addEventListener("input", e=>{
 const q = e.target.value.toLowerCase();
 render(articles.filter(a => a.title.toLowerCase().includes(q)));
});
</script>

</body>
</html>

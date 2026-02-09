<html lang="en">
<head>
<meta charset="UTF-8">
<title>Help Center Demo</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
body {
  margin:0;
  font-family: Arial, Helvetica, sans-serif;
  background:#ffffff;
  color:#111;
}

/* ===== FULL WIDTH HEADER / FOOTER IMAGES ===== */
.header-banner,
.footer-banner {
  width:100%;
  display:block;
}

/* ===== NAV ===== */
header {
  background:#ffffff;
  padding:18px 40px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  border-bottom:1px solid #e5e7eb;
}

.logo {
  font-weight:700;
  font-size:20px;
}

.header-search input {
  padding:10px 14px;
  border-radius:10px;
  border:1px solid #d1d5db;
  width:280px;
}

.signin-btn {
  background:#2563eb;
  border:none;
  color:white;
  padding:10px 16px;
  border-radius:10px;
  font-weight:600;
  cursor:pointer;
}

/* ===== HERO ===== */
.hero {
  background:#f3f4f6;
  text-align:center;
  padding:80px 20px;
}

.hero-search input {
  width:600px;
  max-width:95%;
  padding:18px;
  border-radius:14px;
  border:1px solid #d1d5db;
  font-size:16px;
}

/* ===== FULL WIDTH SECTIONS ===== */
.section {
  padding:60px 6%;
}

/* ===== CATEGORY GRID ===== */
.grid {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
  gap:24px;
}

.card {
  background:white;
  border-radius:16px;
  padding:28px;
  border:1px solid #e5e7eb;
  transition:.25s;
}

.card:hover {
  transform:translateY(-6px);
  box-shadow:0 12px 28px rgba(0,0,0,0.08);
}

/* ===== IMAGE BLOCK — ORIGINAL SIZE ===== */
.image-grid {
  display:grid;
  grid-template-columns:repeat(3, 1fr);
  gap:16px;
  margin-top:30px;
}

.img-wrap {
  overflow:hidden;
  border-radius:16px;
  background:#f9fafb;
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
  background:white;
  border-radius:14px;
  padding:20px;
  border:1px solid #e5e7eb;
  margin-bottom:14px;
}

.tag {
  display:inline-block;
  background:#eef2ff;
  padding:4px 10px;
  border-radius:10px;
  font-size:12px;
  margin-top:8px;
}

/* ===== SUPPORT ===== */
.support {
  background:#eef2ff;
  border-radius:18px;
  padding:50px;
  text-align:center;
}

button {
  padding:14px 22px;
  border-radius:12px;
  border:none;
  font-weight:700;
  cursor:pointer;
  margin:8px;
}

.primary { background:#2563eb; color:white; }
.outline { background:white; border:2px solid #2563eb; color:#2563eb; }

/* ===== FOOTER ===== */
footer {
  text-align:center;
  padding:30px;
  background:#f9fafb;
  color:#555;
}
</style>
</head>

<body>

<!-- HEADER IMAGE -->
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

<!-- CATEGORIES -->
<div class="section">
<h2>Browse Categories</h2>

<div class="grid">
  <div class="card">Account & Login</div>
  <div class="card">Payments</div>
  <div class="card">Integrations</div>
  <div class="card">Developer APIs</div>
</div>
</div>

<!-- IMAGE BLOCK -->
<div class="section">
<h2>Feature Gallery</h2>

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
</div>

<!-- ARTICLES -->
<div class="section">
<h2>Popular Articles</h2>
<div id="articles"></div>
</div>

<!-- SUPPORT -->
<div class="section">
<div class="support">
  <h3>Still need help?</h3>
  <button class="primary">Open Case</button>
  <button class="outline">Start Chat</button>
</div>
</div>

<!-- FOOTER IMAGE -->
<img src="footer.png" class="footer-banner">

<footer>
Demo Help Center UI — Full Width Layout
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

<html lang="en">
<head>
<meta charset="UTF-8">
<title>Help Center Demo</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
body {
  margin:0;
  font-family: Arial, Helvetica, sans-serif;
  background:#f3f4f6;
  color:#111827;
}

/* Header */
header {
  background:#0f172a;
  color:white;
  padding:16px 28px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.logo {
  font-weight:700;
  font-size:18px;
}

.header-search input {
  padding:10px 12px;
  border-radius:8px;
  border:none;
  width:280px;
}

.signin-btn {
  background:#2563eb;
  border:none;
  color:white;
  padding:10px 16px;
  border-radius:8px;
  cursor:pointer;
  font-weight:600;
}

/* Hero */
.hero {
  background:#1f2937;
  color:white;
  text-align:center;
  padding:80px 20px;
}

.hero h1 {
  font-size:40px;
  margin-bottom:10px;
}

.hero-search {
  margin-top:25px;
}

.hero-search input {
  width:560px;
  max-width:92%;
  padding:16px;
  border-radius:14px;
  border:none;
  font-size:16px;
}

/* Layout */
.container {
  max-width:1100px;
  margin:auto;
  padding:50px 20px;
}

/* Categories */
.grid {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:20px;
  margin-top:20px;
}

.card {
  background:white;
  border-radius:14px;
  padding:28px;
  border:1px solid #e5e7eb;
  cursor:pointer;
  transition:.2s;
}

.card:hover {
  transform:translateY(-4px);
  box-shadow:0 8px 20px rgba(0,0,0,0.08);
}

/* Articles */
.article {
  background:white;
  border-radius:12px;
  padding:18px 22px;
  margin-bottom:14px;
  border:1px solid #e5e7eb;
  cursor:pointer;
}

.article:hover {
  background:#f9fafb;
}

.tag {
  display:inline-block;
  background:#e5e7eb;
  padding:4px 8px;
  border-radius:8px;
  font-size:12px;
  margin-top:8px;
}

/* Support Panel */
.support {
  background:#e0e7ff;
  border-radius:16px;
  padding:40px;
  text-align:center;
  margin-top:40px;
}

.support button {
  padding:12px 18px;
  border-radius:10px;
  border:none;
  cursor:pointer;
  font-weight:700;
  margin:8px;
}

.primary {
  background:#2563eb;
  color:white;
}

.outline {
  background:white;
  border:2px solid #2563eb;
  color:#2563eb;
}

/* Footer */
footer {
  background:#0f172a;
  color:#cbd5f1;
  text-align:center;
  padding:30px;
  margin-top:60px;
}
</style>
</head>

<body>

<header>
  <div class="logo">Help Center Demo</div>
  <div class="header-search">
    <input placeholder="Search help articles">
  </div>
  <button class="signin-btn">Sign In</button>
</header>

<section class="hero">
  <h1>How can we help?</h1>
  <p>Search guides, troubleshooting steps, and feature documentation</p>
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
  <div class="card">Security</div>
  <div class="card">Admin Setup</div>
</div>

<h2 style="margin-top:50px;">Popular Articles</h2>

<div id="articles"></div>

<div class="support">
  <h3>Still need help?</h3>
  <p>Create a support case or start a live chat demo</p>
  <button class="primary" onclick="alert('Demo: Open Case Flow')">Open Case</button>
  <button class="outline" onclick="alert('Demo: Start Chatbot')">Start Chat</button>
</div>

</div>

<footer>
Demo Help Center UI — Built for Feature Demonstrations
</footer>

<script>
const articles = [
 {title:"Reset your password", tag:"Account"},
 {title:"Fix login verification errors", tag:"Account"},
 {title:"Configure payment gateway", tag:"Payments"},
 {title:"Refund processing guide", tag:"Payments"},
 {title:"Integration setup steps", tag:"Integrations"},
 {title:"API authentication flow", tag:"Developer"},
 {title:"Create secure access tokens", tag:"Security"}
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

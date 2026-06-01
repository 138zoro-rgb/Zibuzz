<!DOCTYPE html>
<html lang="sq">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>SneakerX</title>

<style>

body{
    margin:0;
    font-family:Arial;
    color:#222;
    background-image:url("https://static.vecteezy.com/system/resources/thumbnails/005/178/782/small_2x/dark-black-glossy-abstract-background-colorful-illustration-in-abstract-style-with-gradient-a-completely-new-template-for-your-business-design-free-vector.jpg");
    background-size:cover;
    background-position:center;
    background-attachment:fixed;
}

/* NAV */
nav{
    background:#111;
    color:#fff;
    padding:18px 40px;
    display:flex;
    justify-content:space-between;
}

/* HERO */
.hero{
    background:linear-gradient(135deg,#111,#444);
    color:#fff;
    text-align:center;
    padding:70px 20px;
}

.hero h1{font-size:48px;margin:0;}

/* GRID */
.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
    padding:40px;
}

/* CARD */
.card{
    background:#fff;
    border-radius:16px;
    overflow:hidden;
    box-shadow:0 6px 15px rgba(0,0,0,.15);
    cursor:pointer;
    transition:.3s;
}

.card:hover{
    transform:translateY(-10px);
}

.card img{
    width:100%;
    height:230px;
    object-fit:cover;
}

.card h3,.card p{
    padding:0 16px;
}

.price{
    padding:0 16px 16px;
    font-weight:bold;
}

/* MODAL */
.modal{
    display:none;
    position:fixed;
    top:0;left:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,.7);
    justify-content:center;
    align-items:center;
    z-index:999;
}

.modal-content{
    background:#fff;
    width:90%;
    max-width:850px;
    border-radius:16px;
    overflow:hidden;
    display:flex;
    flex-wrap:wrap;
}

/* 👟 FIX IMAGES (TË GJITHA NJËSOJ) */
.modal-content img{
    width:400px;
    height:300px;
    object-fit:cover;
    flex-shrink:0;
}

/* INFO */
.info{
    padding:20px;
    flex:1;
}

.buy{
    display:inline-block;
    margin-top:15px;
    padding:10px 20px;
    background:#111;
    color:#fff;
    text-decoration:none;
    border-radius:25px;
    cursor:pointer;
}

/* CLOSE */
.close{
    position:absolute;
    top:20px;
    right:30px;
    font-size:30px;
    color:#fff;
    cursor:pointer;
}

</style>
</head>

<body>

<nav>
<b>SneakerX</b>
<div>Nike | Adidas | New Balance | Puma</div>
</nav>

<div class="hero">
<h1>SNEAKER SHOP</h1>
<p>Kliko për të parë detajet</p>
</div>

<section class="grid">

<!-- NIKE -->
<div class="card" onclick="openModal('nike')">
<img src="https://static.nike.com/a/images/t_PDP_1728_v1/f_auto,q_auto:eco/78c0d78e-5d00-4d93-b100-29a1e3ee909b/NIKE+PEGASUS+PREMIUM.png">
<h3>Nike Pegasus</h3>
<p>Komoditet maksimal</p>
<div class="price">129€</div>
</div>

<!-- ADIDAS -->
<div class="card" onclick="openModal('adidas')">
<img src="https://images.unsplash.com/photo-1518002171953-a080ee817e1f?w=800">
<h3>Adidas Ultraboost</h3>
<p>Dizajn modern</p>
<div class="price">149€</div>
</div>

<!-- NEW BALANCE -->
<div class="card" onclick="openModal('nb')">
<img src="https://sneakernews.com/wp-content/uploads/2023/04/new-balane-9060-grey-day-U9060MD1-5.jpg">
<h3>New Balance 9060</h3>
<p>Stil premium</p>
<div class="price">99€</div>
</div>

<!-- PUMA -->
<div class="card" onclick="openModal('puma')">
<img src="https://images.unsplash.com/photo-1608231387042-66d1773070a5?w=800">
<h3>Puma RS-X</h3>
<p>Sport & stil</p>
<div class="price">119€</div>
</div>

</section>

<!-- MODAL -->
<div id="modal" class="modal" onclick="closeModal(event)">
<span class="close">&times;</span>
<div class="modal-content" id="modalContent"></div>
</div>

<script>

function openModal(product){

let content="";

if(product=="nike"){
content=`
<img src="https://static.nike.com/a/images/t_PDP_1728_v1/f_auto,q_auto:eco/78c0d78e-5d00-4d93-b100-29a1e3ee909b/NIKE+PEGASUS+PREMIUM.png">
<div class="info">
<h2>Nike Pegasus</h2>
<p>Patika perfekte për vrap dhe përdorim ditor.</p>
<h3>129€</h3>
<a class="buy">Bli Tani</a>
</div>`;
}

if(product=="adidas"){
content=`
<img src="https://images.unsplash.com/photo-1518002171953-a080ee817e1f?w=800">
<div class="info">
<h2>Adidas Ultraboost</h2>
<p>Performancë dhe stil modern.</p>
<h3>149€</h3>
<a class="buy">Bli Tani</a>
</div>`;
}

if(product=="nb"){
content=`
<img src="https://sneakernews.com/wp-content/uploads/2023/04/new-balane-9060-grey-day-U9060MD1-5.jpg">
<div class="info">
<h2>New Balance 9060</h2>
<p>Komoditet premium dhe stil unik.</p>
<h3>99€</h3>
<a class="buy">Bli Tani</a>
</div>`;
}

if(product=="puma"){
content=`
<img src="https://images.unsplash.com/photo-1608231387042-66d1773070a5?w=800">
<div class="info">
<h2>Puma RS-X</h2>
<p>Sport dhe stil modern.</p>
<h3>119€</h3>
<a class="buy">Bli Tani</a>
</div>`;
}

document.getElementById("modalContent").innerHTML=content;
document.getElementById("modal").style.display="flex";
}

function closeModal(e){
if(e.target.id=="modal" || e.target.className=="close"){
document.getElementById("modal").style.display="none";
}
}

</script>

</body>
</html>

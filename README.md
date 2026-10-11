# amarshopnno-
Alhamdulillah 

<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Amar Shop | অনলাইন শপ</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f5f6fa;color:#222}
header{background:#087f5b;color:white;padding:20px 14px;text-align:center}
header h1{margin:0 0 8px}
header p{margin:5px}
nav{background:white;padding:12px;text-align:center;position:sticky;top:0}
nav a{color:#087f5b;text-decoration:none;font-weight:bold;margin:0 8px}
.wrap{max-width:1000px;margin:auto;padding:14px}
input,select,textarea,button{font:inherit;padding:11px;border:1px solid #ccc;border-radius:7px;width:100%}
.search{margin:8px 0 14px}
.categories{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:14px}
.categories button{width:auto;background:white}
.products{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.card{background:white;padding:12px;border-radius:12px;box-shadow:0 2px 8px #0001}
.photo{height:105px;background:#e7f5ef;border-radius:8px;display:grid;place-items:center;font-size:42px}
.card h3{font-size:16px;margin:10px 0}
.price{font-weight:bold;color:#087f5b}
.card button,.primary{background:#087f5b;color:white;border:0;margin-top:8px;cursor:pointer}
section{margin:22px 0;background:white;padding:16px;border-radius:12px}
section h2{font-size:21px}
.line{display:flex;gap:8px;align-items:center;margin:10px 0}
.line button{width:auto}
.small{font-size:13px;color:#555}
footer{background:#173b32;color:white;text-align:center;padding:20px}
@media(min-width:650px){.products{grid-template-columns:repeat(4,minmax(0,1fr))}}
</style>
</head>
<body>
<header>
<h1>🛍️ Amar Shop</h1>
<p>আপনার পছন্দের পণ্য, আপনার হাতেই</p>
<p>সারা বাংলাদেশে ডেলিভারি</p>
</header>
<nav>
<a href="#products">পণ্য</a>
<a href="#cart">কার্ট</a>
<a href="#order">অর্ডার</a>
</nav>

<main class="wrap">
<h2 id="products">আমাদের পণ্য</h2>
<input class="search" id="search" placeholder="পণ্যের নাম লিখে খুঁজুন..." oninput="render()">
<div class="categories">
<button onclick="setCat('সব')">সব পণ্য</button>
<button onclick="setCat('ফ্যাশন')">ফ্যাশন</button>
<button onclick="setCat('খাবার')">খাবার</button>
<button onclick="setCat('ইলেকট্রনিক্স')">ইলেকট্রনিক্স</button>
<button onclick="setCat('ঘর')">ঘর ও পরিবার</button>
</div>
<div class="products" id="productsList"></div>

<section id="cart">
<h2>🛒 আপনার কার্ট</h2>
<div id="cartList">এখনো কোনো পণ্য বাছাই করেননি।</div>
<p>মোট: ৳<strong id="total">0</strong></p>
<button class="primary" onclick="goOrder()">অর্ডার করতে এগিয়ে যান</button>
</section>

<section id="order">
<h2>📦 অর্ডার ফর্ম</h2>
<form id="orderForm">
<label>আপনার নাম</label>
<input id="name" required placeholder="সম্পূর্ণ নাম">
<br><br>
<label>মোবাইল নম্বর</label>
<input id="phone" required inputmode="tel" placeholder="01XXXXXXXXX">
<br><br>
<label>সম্পূর্ণ ঠিকানা</label>
<textarea id="address" required placeholder="গ্রাম/এলাকা, উপজেলা, জেলা"></textarea>
<br><br>
<label>পেমেন্ট পদ্ধতি</label>
<select id="payment">
<option>ক্যাশ অন ডেলিভারি</option>
<option>বিকাশ (ম্যানুয়াল পেমেন্ট)</option>
<option>নগদ (ম্যানুয়াল পেমেন্ট)</option>
</select>
<p class="small">বিকাশ/নগদ বাছলে পেমেন্ট করার আগে দোকানের সঙ্গে নম্বর ও মোট টাকা নিশ্চিত করুন।</p>
<button class="primary" type="submit">WhatsApp-এ অর্ডার পাঠান</button>
<button type="button" onclick="copyOrder()">ফর্মের অর্ডার কপি করুন</button>
</form>
<p class="small">এই ফর্মের তথ্য নিজে থেকে সার্ভারে সংরক্ষিত হয় না। WhatsApp-এ পাঠালে বার্তাটি দেখে অর্ডার নিশ্চিত করতে হবে।</p>
</section>

<section>
<h2>যোগাযোগ</h2>
<p>ফোন: <a href="tel:01626874859">01626874859</a></p>
<p>বিকাশ: 01581503259</p>
<p>নগদ: 01581503259</p>
<p>ডেলিভারি: সারা বাংলাদেশ</p>
<a href="https://wa.me/8801626874859">WhatsApp-এ যোগাযোগ করুন</a>
</section>
</main>
<footer>© Amar Shop — আপনার অনলাইন দোকান</footer>

<script>
const products=[
{id:1,name:"স্টাইলিশ জুতা",price:650,cat:"ফ্যাশন",emoji:"👟"},
{id:2,name:"ফ্যাশন ব্যাগ",price:450,cat:"ফ্যাশন",emoji:"👜"},
{id:3,name:"চিংড়ি বালাচাও",price:250,cat:"খাবার",emoji:"🍤"},
{id:4,name:"মোবাইল চার্জার",price:350,cat:"ইলেকট্রনিক্স",emoji:"🔌"},
{id:5,name:"মোবাইল কভার",price:150,cat:"ইলেকট্রনিক্স",emoji:"📱"},
{id:6,name:"বিছানার চাদর",price:550,cat:"ঘর",emoji:"🛏️"},
{id:7,name:"পানির বোতল",price:180,cat:"ঘর",emoji:"🧴"},
{id:8,name:"টি-শার্ট",price:300,cat:"ফ্যাশন",emoji:"👕"}
];
let cart={},category="সব";
function setCat(c){category=c;render()}
function render(){
let q=document.getElementById("search").value.toLowerCase();
let list=products.filter(p=>(category==="সব"||p.cat===category)&&p.name.toLowerCase().includes(q));
document.getElementById("productsList").innerHTML=list.map(p=>
`<article class="card"><div class="photo">${p.emoji}</div><h3>${p.name}</h3><p class="price">৳${p.price}</p><button onclick="add(${p.id})">কার্টে যোগ করুন</button></article>`
).join("")||"কোনো পণ্য পাওয়া যায়নি।";
showCart();
}
function add(id){cart[id]=(cart[id]||0)+1;showCart()}
function change(id,delta){cart[id]=(cart[id]||0)+delta;if(cart[id]<=0)delete cart[id];showCart()}
function showCart(){
let items=products.filter(p=>cart[p.id]);
document.getElementById("cartList").innerHTML=items.length?items.map(p=>
`<div class="line"><div style="flex:1">${p.name}<br>৳${p.price} × ${cart[p.id]}</div><button onclick="change(${p.id},-1)">−</button><button onclick="change(${p.id},1)">+</button></div>`
).join(""):"এখনো কোনো পণ্য বাছাই করেননি।";
document.getElementById("total").textContent=items.reduce((s,p)=>s+p.price*cart[p.id],0);
}
function goOrder(){document.getElementById("order").scrollIntoView({behavior:"smooth"})}
function orderText(){
let items=products.filter(p=>cart[p.id]);
if(!items.length){alert("আগে কার্টে পণ্য যোগ করুন।");return ""}
let total=items.reduce((s,p)=>s+p.price*cart[p.id],0);
return "Amar Shop অর্ডার%0Aপণ্য: "+items.map(p=>p.name+" × "+cart[p.id]+" = ৳"+p.price*cart[p.id]).join("%0A")+"%0Aমোট পণ্যমূল্য: ৳"+total+"%0Aনাম: "+encodeURIComponent(document.getElementById("name").value)+"%0Aফোন: "+encodeURIComponent(document.getElementById("phone").value)+"%0Aঠিকানা: "+encodeURIComponent(document.getElementById("address").value)+"%0Aপেমেন্ট: "+encodeURIComponent(document.getElementById("payment").value);
}
document.getElementById("orderForm").addEventListener("submit",function(e){
e.preventDefault();
if(!Object.keys(cart).length){alert("আগে কার্টে পণ্য যোগ করুন।");return}
location.href="https://wa.me/8801626874859?text="+orderText();
});
function copyOrder(){
let t=orderText();if(!t)return;
let a=document.createElement("a");
a.href="https://wa.me/8801626874859?text="+t;
a.target="_blank";a.rel="noopener";a.click();
}
render();
</script>
</body>
</html>

# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SS DYNAMIC MARKETPLACE PRO v1.0</title>
<style>
body{font-family:Arial,sans-serif;margin:0;background:#111;color:#fff}
header{background:#b30000;padding:20px;text-align:center}
.container{max-width:1200px;margin:auto;padding:20px}
.card{background:#1e1e1e;padding:15px;border-radius:10px;margin:10px 0}
input,textarea,select{width:100%;padding:10px;margin:5px 0}
button{padding:10px 15px;background:#d40000;color:#fff;border:none;cursor:pointer}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:15px}
.product img{width:100%;height:180px;object-fit:cover}
.hidden{display:none}
.cart{position:fixed;right:10px;top:10px;background:#222;padding:10px;border-radius:8px}
</style>
</head>
<body>
<header>
<h1>SS DYNAMIC MARKETPLACE PRO v1.0</h1>
<p>Admin Product Management • Shopping Cart • WhatsApp Checkout</p>
</header>

<div class="cart">
Cart: <span id="cartCount">0</span>
<button onclick="viewCart()">View</button>
</div>

<div class="container">

<div class="card">
<h2>Admin Login</h2>
<input id="adminId" placeholder="Admin ID">
<input id="adminPass" type="password" placeholder="Password">
<button onclick="login()">Login</button>
</div>

<div id="adminPanel" class="card hidden">
<h2>Add Product</h2>
<input id="name" placeholder="Product Name">
<input id="price" type="number" placeholder="Price">
<input id="category" placeholder="Category">
<input id="days" placeholder="Estimated Days">
<textarea id="desc" placeholder="Description"></textarea>
<input id="image" type="file" accept="image/*">
<button onclick="addProduct()">Add Product</button>
</div>

<h2>Product Gallery</h2>
<div id="products" class="grid"></div>

</div>

<script>
const ADMIN_ID="SS DYNAMIC";
const ADMIN_PASS="#SSDYNAMIC303677";
let cart=JSON.parse(localStorage.getItem("cart")||"[]");
document.getElementById("cartCount").innerText=cart.length;

function login(){
 if(document.getElementById("adminId").value===ADMIN_ID &&
    document.getElementById("adminPass").value===ADMIN_PASS){
    document.getElementById("adminPanel").classList.remove("hidden");
    alert("Admin Login Success");
 } else alert("Invalid Login");
}

function sku(){ return "SKU-"+Date.now(); }

function saveProducts(p){ localStorage.setItem("products",JSON.stringify(p)); }

function loadProducts(){
 return JSON.parse(localStorage.getItem("products")||"[]");
}

function addProduct(){
 const file=document.getElementById("image").files[0];
 const reader=new FileReader();
 reader.onload=function(){
   const products=loadProducts();
   products.push({
    id:Date.now(),
    sku:sku(),
    name:name.value,
    price:price.value,
    category:category.value,
    days:days.value,
    desc:desc.value,
    image:reader.result
   });
   saveProducts(products);
   render();
 };
 if(file) reader.readAsDataURL(file);
}

function deleteProduct(id){
 let products=loadProducts().filter(x=>x.id!==id);
 saveProducts(products);
 render();
}

function addCart(id){
 let products=loadProducts();
 let p=products.find(x=>x.id===id);
 cart.push(p);
 localStorage.setItem("cart",JSON.stringify(cart));
 document.getElementById("cartCount").innerText=cart.length;
}

function render(){
 let products=loadProducts();
 let html="";
 products.forEach(p=>{
  html+=`
  <div class="card product">
   <img src="${p.image}">
   <h3>${p.name}</h3>
   <p>${p.sku}</p>
   <p>RM ${p.price}</p>
   <p>${p.category}</p>
   <p>${p.days} Days</p>
   <p>${p.desc}</p>
   <button onclick="addCart(${p.id})">Add To Cart</button>
   <button onclick="deleteProduct(${p.id})">Delete</button>
  </div>`;
 });
 document.getElementById("products").innerHTML=html;
}

function viewCart(){
 if(cart.length===0){alert("Cart Empty");return;}
 let name=prompt("Customer Name:");
 let phone=prompt("WhatsApp Number:");
 let email=prompt("Email:");
 let address=prompt("Address:");
 let orderId="ORD-"+Date.now();
 let msg="*SS DYNAMIC ORDER*%0AOrder ID:"+orderId+"%0AName:"+name+"%0APhone:"+phone+"%0AEmail:"+email+"%0AAddress:"+address+"%0A%0A";
 cart.forEach(x=>{
   msg+=x.name+" - RM"+x.price+"%0A";
 });
 window.open("https://wa.me/?text="+msg,"_blank");
}
render();
</script>
</body>

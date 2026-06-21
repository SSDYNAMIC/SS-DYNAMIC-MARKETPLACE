# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0"><title>SS DYNAMIC MARKETPLACE</title><style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Segoe UI,Arial,sans-serif;
}

:root{
--primary:#ff0000;
--secondary:#111111;
--dark:#000000;
--light:#ffffff;
--gray:#1f1f1f;
--success:#00c853;
}

body{
background:#0a0a0a;
color:white;
}

header{
background:linear-gradient(135deg,#ff0000,#000000);
padding:20px;
position:sticky;
top:0;
z-index:999;
box-shadow:0 3px 15px rgba(0,0,0,.5);
}

.logo{
font-size:32px;
font-weight:bold;
text-align:center;
}

.subtitle{
text-align:center;
margin-top:5px;
font-size:14px;
opacity:.9;
}

.top-bar{
display:flex;
justify-content:space-between;
align-items:center;
margin-top:15px;
flex-wrap:wrap;
gap:10px;
}

.search-box{
flex:1;
min-width:250px;
}

.search-box input{
width:100%;
padding:12px;
border:none;
border-radius:10px;
}

.cart-btn{
background:var(--success);
border:none;
color:white;
padding:12px 20px;
border-radius:10px;
cursor:pointer;
font-weight:bold;
}

.admin-btn{
background:var(--primary);
border:none;
color:white;
padding:12px 20px;
border-radius:10px;
cursor:pointer;
font-weight:bold;
}

.hero{
height:350px;
display:flex;
justify-content:center;
align-items:center;
text-align:center;
background:
linear-gradient(rgba(0,0,0,.6),rgba(0,0,0,.6)),
url('https://images.unsplash.com/photo-1518770660439-4636190af475');
background-size:cover;
background-position:center;
}

.hero h1{
font-size:48px;
}

.hero p{
margin-top:15px;
font-size:18px;
}

.container{
width:95%;
max-width:1400px;
margin:auto;
padding:30px 0;
}

.section-title{
font-size:30px;
margin-bottom:20px;
border-left:5px solid red;
padding-left:10px;
}

.category-filter{
display:flex;
flex-wrap:wrap;
gap:10px;
margin-bottom:20px;
}

.category-filter button{
padding:10px 20px;
border:none;
border-radius:30px;
cursor:pointer;
background:#222;
color:white;
}

.category-filter button:hover{
background:red;
}

.products-grid{
display:grid;
grid-template-columns:repeat(auto-fill,minmax(280px,1fr));
gap:20px;
}

.product-card{
background:#161616;
border-radius:15px;
overflow:hidden;
transition:.3s;
border:1px solid #333;
}

.product-card:hover{
transform:translateY(-5px);
}

.product-image{
height:220px;
overflow:hidden;
}

.product-image img{
width:100%;
height:100%;
object-fit:cover;
}

.product-content{
padding:15px;
}

.product-title{
font-size:20px;
font-weight:bold;
margin-bottom:10px;
}

.product-price{
font-size:24px;
font-weight:bold;
color:#00ff66;
}

.product-category{
display:inline-block;
padding:5px 12px;
background:red;
border-radius:20px;
font-size:12px;
margin-top:10px;
}

.product-desc{
margin-top:10px;
font-size:14px;
line-height:1.5;
}

.product-sku{
margin-top:10px;
font-size:12px;
color:#aaa;
}

.product-estimate{
margin-top:10px;
font-size:13px;
color:#ffcc00;
}

.product-buttons{
display:flex;
gap:10px;
margin-top:15px;
}

.btn{
flex:1;
padding:10px;
border:none;
border-radius:8px;
cursor:pointer;
font-weight:bold;
}

.btn-cart{
background:#00c853;
color:white;
}

.btn-view{
background:#ff0000;
color:white;
}

.modal{
display:none;
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,.8);
z-index:1000;
overflow:auto;
}

.modal-content{
width:95%;
max-width:700px;
margin:50px auto;
background:#111;
padding:25px;
border-radius:15px;
}

.close{
float:right;
font-size:28px;
cursor:pointer;
}

input,
select,
textarea{
width:100%;
padding:12px;
margin-top:10px;
margin-bottom:15px;
border:none;
border-radius:10px;
background:#222;
color:white;
}

button{
cursor:pointer;
}

.form-btn{
background:red;
color:white;
padding:12px;
border:none;
border-radius:10px;
font-weight:bold;
width:100%;
}

.admin-panel{
display:none;
background:#151515;
padding:20px;
border-radius:15px;
margin-top:20px;
}

.cart-panel{
display:none;
position:fixed;
right:0;
top:0;
width:400px;
max-width:100%;
height:100%;
background:#111;
padding:20px;
overflow:auto;
z-index:1200;
box-shadow:-5px 0 20px rgba(0,0,0,.5);
}

.cart-header{
display:flex;
justify-content:space-between;
align-items:center;
margin-bottom:20px;
}

.cart-item{
background:#1f1f1f;
padding:10px;
border-radius:10px;
margin-bottom:10px;
}

.cart-total{
font-size:22px;
font-weight:bold;
margin-top:20px;
color:#00ff66;
}

footer{
background:#000;
padding:40px;
margin-top:50px;
text-align:center;
}

footer h3{
color:red;
margin-bottom:10px;
}

.badge{
background:red;
padding:3px 8px;
border-radius:20px;
font-size:12px;
margin-left:5px;
}

@media(max-width:768px){

.hero h1{
font-size:32px;
}

.top-bar{
flex-direction:column;
}

.search-box{
width:100%;
}

.cart-panel{
width:100%;
}

}

</style></head><body><header><div class="logo">
SS DYNAMIC MARKETPLACE
</div><div class="subtitle">
Only Marketplace Owners Can Add & Delete Product Listings
</div><div class="top-bar"><div class="search-box">
<input
type="text"
id="searchInput"
placeholder="Search Product..."
>
</div><button
class="cart-btn"
onclick="openCart()">

🛒 CART
<span id="cartCount" class="badge">0</span>

</button><button
class="admin-btn"
onclick="openAdminLogin()">

ADMIN LOGIN

</button></div></header><section class="hero"><div><h1>
SS DYNAMIC MARKETPLACE
</h1><p>
Professional Marketplace System
</p><p>
Shopping Cart • WhatsApp Checkout • Auto SKU
</p></div></section><div class="container"><h2 class="section-title">
PRODUCT CATEGORIES
</h2><div class="category-filter"><button onclick="filterCategory('all')">
ALL
</button><button onclick="filterCategory('electronics')">
ELECTRONICS
</button><button onclick="filterCategory('accessories')">
ACCESSORIES
</button><button onclick="filterCategory('tools')">
TOOLS
</button><button onclick="filterCategory('others')">
OTHERS
</button></div><h2 class="section-title">
PRODUCT LISTINGS
</h2><div
id="productContainer"
class="products-grid"></div><div
id="adminPanel"
class="admin-panel"><h2>
ADMIN PRODUCT MANAGEMENT
</h2><p>
(Visible Only After Login)
</p><hr style="margin:20px 0"><h3>
ADD NEW PRODUCT
</h3><form id="productForm"><input
type="text"
id="productName"
placeholder="Product Name">

<input
type="number"
id="productPrice"
placeholder="Price">

<select id="productCategory"><option value="">
Select Category
</option><option value="electronics">
Electronics
</option><option value="accessories">
Accessories
</option><option value="tools">
Tools
</option><option value="others">
Others
</option></select><input
type="number"
id="deliveryDays"
placeholder="Estimated Delivery Days">

<textarea
id="productDescription"
placeholder="Product Description">
</textarea><input
type="file"
id="productImage"
accept="image/*">

<button
type="button"
class="form-btn"
onclick="addProduct()">

ADD PRODUCT

</button></form><div
id="adminProductList"
style="margin-top:30px"></div></div></div><div
id="adminLoginModal"
class="modal"><div class="modal-content"><span
class="close"
onclick="closeAdminLogin()">

×

</span><h2>
ADMIN LOGIN
</h2><input
type="text"
id="adminId"
placeholder="Admin ID">

<input
type="password"
id="adminPassword"
placeholder="Password">

<button
class="form-btn"
onclick="adminLogin()">

LOGIN

</button></div></div><div
id="cartPanel"
class="cart-panel"><div class="cart-header"><h2>
SHOPPING CART
</h2><button
class="admin-btn"
onclick="closeCart()">

CLOSE

</button></div><div id="cartItems"></div><div
class="cart-total"
id="cartTotal">TOTAL: RM0

</div><hr style="margin:20px 0"><h3>
CUSTOMER ORDER FORM
</h3><input
type="text"
id="customerName"
placeholder="Name">

<input
type="text"
id="customerWhatsapp"
placeholder="WhatsApp Number">

<input
type="email"
id="customerEmail"
placeholder="Email">

<textarea
id="customerAddress"
placeholder="Address">
</textarea><button
class="form-btn"
onclick="checkoutWhatsApp()">

ORDER VIA WHATSAPP

</button></div><footer><h3>
SS DYNAMIC MARKETPLACE
</h3><p>
Professional Product Listing & Ordering System
</p><p>
Version 1.0 Marketplace Foundation
</p></footer><script>

/* =====================================================
PART 2 - JAVASCRIPT CORE ENGINE
PASTE INSIDE:

<script>

/* PART 2 START HERE */

===================================================== */

// ==========================================
// CONFIG
// ==========================================

const ADMIN_ID = "SS DYNAMIC";
const ADMIN_PASSWORD = "#SSDYNAMIC303677";

let products = JSON.parse(localStorage.getItem("ssdynamic_products")) || [];
let cart = JSON.parse(localStorage.getItem("ssdynamic_cart")) || [];

let currentFilter = "all";

// ==========================================
// INIT
// ==========================================

window.onload = function(){

loadProducts();
renderProducts();
updateCartCount();

};

// ==========================================
// ADMIN LOGIN
// ==========================================

function openAdminLogin(){
document.getElementById("adminLoginModal").style.display="block";
}

function closeAdminLogin(){
document.getElementById("adminLoginModal").style.display="none";
}

function adminLogin(){

let id =
document.getElementById("adminId").value;

let password =
document.getElementById("adminPassword").value;

if(
id === ADMIN_ID &&
password === ADMIN_PASSWORD
){

alert("Admin Login Success");

document.getElementById(
"adminPanel"
).style.display="block";

closeAdminLogin();

renderAdminProducts();

}
else{

alert("Invalid Admin ID or Password");

}

}

function adminLogout(){

document.getElementById(
"adminPanel"
).style.display="none";

alert("Logged Out");

}

// ==========================================
// PRODUCT STORAGE
// ==========================================

function saveProducts(){

localStorage.setItem(
"ssdynamic_products",
JSON.stringify(products)
);

}

function loadProducts(){

products =
JSON.parse(
localStorage.getItem(
"ssdynamic_products"
)
) || [];

}

// ==========================================
// SKU GENERATOR
// ==========================================

function generateSKU(){

let random =
Math.floor(
100000 + Math.random() * 900000
);

return "SSD-" + random;

}

// ==========================================
// PRODUCT ID
// ==========================================

function generateProductId(){

return Date.now();

}

// ==========================================
// IMAGE TO BASE64
// ==========================================

function convertImageToBase64(
file,
callback
){

const reader = new FileReader();

reader.onload = function(e){

callback(e.target.result);

};

reader.readAsDataURL(file);

}

// ==========================================
// ADD PRODUCT
// ==========================================

function addProduct(){

const name =
document.getElementById(
"productName"
).value;

const price =
document.getElementById(
"productPrice"
).value;

const category =
document.getElementById(
"productCategory"
).value;

const delivery =
document.getElementById(
"deliveryDays"
).value;

const description =
document.getElementById(
"productDescription"
).value;

const imageFile =
document.getElementById(
"productImage"
).files[0];

if(
!name ||
!price ||
!category
){

alert(
"Please complete all required fields"
);

return;

}

if(imageFile){

convertImageToBase64(
imageFile,
function(base64Image){

let product = {

id: generateProductId(),

sku: generateSKU(),

name: name,

price: parseFloat(price),

category: category,

delivery: delivery,

description: description,

image: base64Image

};

products.push(product);

saveProducts();

renderProducts();

renderAdminProducts();

document.getElementById(
"productForm"
).reset();

alert(
"Product Added Successfully"
);

}
);

}
else{

let product = {

id: generateProductId(),

sku: generateSKU(),

name: name,

price: parseFloat(price),

category: category,

delivery: delivery,

description: description,

image:
"https://via.placeholder.com/400x300?text=SS+DYNAMIC"

};

products.push(product);

saveProducts();

renderProducts();

renderAdminProducts();

document.getElementById(
"productForm"
).reset();

alert(
"Product Added Successfully"
);

}

}

// ==========================================
// DELETE PRODUCT
// ==========================================

function deleteProduct(id){

let confirmDelete =
confirm(
"Delete this product?"
);

if(!confirmDelete) return;

products =
products.filter(
product =>
product.id !== id
);

saveProducts();

renderProducts();

renderAdminProducts();

}

// ==========================================
// ADMIN PRODUCT LIST
// ==========================================

function renderAdminProducts(){

const container =
document.getElementById(
"adminProductList"
);

if(!container) return;

let html = "";

products.forEach(product=>{

html += `

<div
style="
background:#222;
padding:15px;
border-radius:10px;
margin-bottom:10px;
">

<b>${product.name}</b>

<br>

SKU:
${product.sku}

<br>

RM
${product.price}

<br><br>

<button
onclick="deleteProduct(${product.id})"
style="
background:red;
border:none;
padding:8px 15px;
color:white;
border-radius:5px;
cursor:pointer;
">

DELETE

</button>

</div>

`;

});

container.innerHTML = html;

}

// ==========================================
// FILTER PRODUCTS
// ==========================================

function filterCategory(category){

currentFilter = category;

renderProducts();

}

// ==========================================
// SEARCH PRODUCTS
// ==========================================

document.addEventListener(
"input",
function(e){

if(
e.target.id === "searchInput"
){

renderProducts();

}

}
);

// ==========================================
// PRODUCT GRID
// ==========================================

function renderProducts(){

const container =
document.getElementById(
"productContainer"
);

if(!container) return;

let searchText =
document.getElementById(
"searchInput"
).value
.toLowerCase();

let filteredProducts =
products.filter(product=>{

let categoryMatch =
currentFilter==="all"
||
product.category===currentFilter;

let searchMatch =
product.name
.toLowerCase()
.includes(searchText);

return (
categoryMatch &&
searchMatch
);

});

let html = "";

filteredProducts.forEach(product=>{

html += `

<div class="product-card">

<div class="product-image">

<img
src="${product.image}"
alt="${product.name}">

</div>

<div class="product-content">

<div class="product-title">
${product.name}
</div>

<div class="product-price">
RM ${product.price}
</div>

<div class="product-category">
${product.category}
</div>

<div class="product-desc">
${product.description}
</div>

<div class="product-sku">
SKU:
${product.sku}
</div>

<div class="product-estimate">
Estimated:
${product.delivery} Day(s)
</div>

<div class="product-buttons">

<button
class="btn btn-cart"
onclick="addToCart(${product.id})">

ADD TO CART

</button>

</div>

</div>

</div>

`;

});

if(filteredProducts.length===0){

html = `
<div style="padding:30px;">
No Products Found
</div>
`;

}

container.innerHTML = html;

}

/* =====================================================
PART 3 - SHOPPING CART, ORDER SYSTEM,
WHATSAPP CHECKOUT & FINAL INTEGRATION

PASTE BELOW PART 2
INSIDE THE SAME <script> TAG

===================================================== */

// ==========================================
// CART STORAGE
// ==========================================

function saveCart(){

localStorage.setItem(
"ssdynamic_cart",
JSON.stringify(cart)
);

}

// ==========================================
// CART PANEL
// ==========================================

function openCart(){

document.getElementById(
"cartPanel"
).style.display="block";

renderCart();

}

function closeCart(){

document.getElementById(
"cartPanel"
).style.display="none";

}

// ==========================================
// ADD TO CART
// ==========================================

function addToCart(productId){

const product =
products.find(
p => p.id === productId
);

if(!product) return;

const existing =
cart.find(
item => item.id === productId
);

if(existing){

existing.qty++;

}else{

cart.push({

id: product.id,
sku: product.sku,
name: product.name,
price: product.price,
image: product.image,
qty: 1

});

}

saveCart();

renderCart();

updateCartCount();

alert(
product.name +
" added to cart"
);

}

// ==========================================
// REMOVE CART ITEM
// ==========================================

function removeCartItem(productId){

cart =
cart.filter(
item => item.id !== productId
);

saveCart();

renderCart();

updateCartCount();

}

// ==========================================
// INCREASE QTY
// ==========================================

function increaseQty(productId){

const item =
cart.find(
i => i.id === productId
);

if(item){

item.qty++;

saveCart();

renderCart();

updateCartCount();

}

}

// ==========================================
// DECREASE QTY
// ==========================================

function decreaseQty(productId){

const item =
cart.find(
i => i.id === productId
);

if(!item) return;

item.qty--;

if(item.qty <= 0){

removeCartItem(productId);

return;

}

saveCart();

renderCart();

updateCartCount();

}

// ==========================================
// CART COUNTER
// ==========================================

function updateCartCount(){

const totalItems =
cart.reduce(
(sum,item)=>
sum + item.qty,
0
);

const counter =
document.getElementById(
"cartCount"
);

if(counter){

counter.innerText =
totalItems;

}

}

// ==========================================
// RENDER CART
// ==========================================

function renderCart(){

const cartItems =
document.getElementById(
"cartItems"
);

const cartTotal =
document.getElementById(
"cartTotal"
);

if(!cartItems) return;

let html = "";

let total = 0;

cart.forEach(item=>{

let subtotal =
item.price * item.qty;

total += subtotal;

html += `

<div class="cart-item"><b>
${item.name}
</b><br>SKU:
${item.sku}

<br>RM ${item.price}

<br><br>

<div style="
display:flex;
gap:10px;
align-items:center;
"><button
onclick="decreaseQty(${item.id})">

- 

</button><span>${item.qty}

</span><button
onclick="increaseQty(${item.id})">

+ 

</button></div><br>Subtotal:
RM ${subtotal.toFixed(2)}

<br><br>

<button
onclick="removeCartItem(${item.id})"
style="
background:red;
color:white;
border:none;
padding:8px;
border-radius:5px;
">

REMOVE

</button></div>`;

});

if(cart.length===0){

html = `

<p>
Your cart is empty
</p>
`;}

cartItems.innerHTML = html;

cartTotal.innerHTML =
"TOTAL: RM " +
total.toFixed(2);

}

// ==========================================
// ORDER ID GENERATOR
// ==========================================

function generateOrderId(){

let now =
new Date();

let random =
Math.floor(
1000 + Math.random()*9000
);

return "SSD-ORDER-" +
now.getFullYear() +
(now.getMonth()+1) +
now.getDate() +
"-" +
random;

}

// ==========================================
// WHATSAPP CHECKOUT
// ==========================================

function checkoutWhatsApp(){

if(cart.length===0){

alert(
"Cart is empty"
);

return;

}

let name =
document.getElementById(
"customerName"
).value;

let whatsapp =
document.getElementById(
"customerWhatsapp"
).value;

let email =
document.getElementById(
"customerEmail"
).value;

let address =
document.getElementById(
"customerAddress"
).value;

if(
!name ||
!whatsapp
){

alert(
"Please enter customer information"
);

return;

}

let orderId =
generateOrderId();

let total = 0;

let message =

"SS DYNAMIC MARKETPLACE ORDER%0A%0A" +

"Order ID: " +
orderId +
"%0A" +

"Customer Name: " +
name +
"%0A" +

"WhatsApp: " +
whatsapp +
"%0A" +

"Email: " +
email +
"%0A" +

"Address: " +
address +
"%0A%0A" +

"====================%0A" +

"ORDER ITEMS%0A" +

"====================%0A";

cart.forEach(item=>{

let subtotal =
item.price *
item.qty;

total += subtotal;

message +=

item.name +
"%0A" +

"SKU: " +
item.sku +
"%0A" +

"Qty: " +
item.qty +
"%0A" +

"Price: RM " +
item.price +
"%0A" +

"Subtotal: RM " +
subtotal.toFixed(2) +
"%0A%0A";

});

message +=

"====================%0A" +

"TOTAL: RM " +
total.toFixed(2) +
"%0A" +

"====================%0A%0A" +

"Thank You.";

window.open(

"https://wa.me/601151453147?text=" +
message,

"_blank"

);

cart = [];

saveCart();

renderCart();

updateCartCount();

}

// ==========================================
// AUTO CLOSE MODAL
// ==========================================

window.onclick = function(event){

const modal =
document.getElementById(
"adminLoginModal"
);

if(event.target === modal){

modal.style.display="none";

}

};

// ==========================================
// DEMO PRODUCTS
// FIRST RUN ONLY
// ==========================================

if(
localStorage.getItem(
"ssdynamic_products"
) === null
){

products = [

{
id:1,
sku:"SSD-100001",
name:"Sample Product 1",
price:99,
category:"electronics",
delivery:3,
description:"SS Dynamic Demo Product",
image:"https://via.placeholder.com/400x300?text=SS+DYNAMIC"
},

{
id:2,
sku:"SSD-100002",
name:"Sample Product 2",
price:199,
category:"accessories",
delivery:5,
description:"SS Dynamic Demo Product",
image:"https://via.placeholder.com/400x300?text=SS+DYNAMIC"
}

];

saveProducts();

}

// ==========================================
// FINAL INITIALIZATION
// ==========================================

loadProducts();

renderProducts();

renderCart();

updateCartCount();

console.log(
"SS DYNAMIC MARKETPLACE READY"
);

/*</script></body>

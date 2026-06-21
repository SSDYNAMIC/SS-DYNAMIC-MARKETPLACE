# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SS DYNAMIC MARKETPLACE</title><style>
/*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Segoe UI',Tahoma,Geneva,Verdana,sans-serif;
}

:root{
--primary:#ff0000;
--secondary:#cc0000;
--dark:#0f0f0f;
--card:#1a1a1a;
--border:#333;
--text:#ffffff;
--muted:#aaaaaa;
--success:#00c853;
}

body{
background:#111;
color:#fff;
line-height:1.6;
min-height:100vh;
}

/* HEADER */

.header{
background:linear-gradient(135deg,#000,#8b0000,#000);
padding:25px;
display:flex;
justify-content:space-between;
align-items:center;
flex-wrap:wrap;
border-bottom:3px solid var(--primary);
box-shadow:0 5px 20px rgba(255,0,0,0.2);
}

.logo-area h1{
font-size:2rem;
font-weight:800;
color:#fff;
}

.logo-area p{
color:#ddd;
margin-top:5px;
}

.header-right{
display:flex;
gap:15px;
flex-wrap:wrap;
}

.header-right span{
background:#1e1e1e;
padding:10px 18px;
border-radius:10px;
border:1px solid #444;
font-weight:600;
}

/* SECTIONS */

section{
padding:25px;
max-width:1400px;
margin:auto;
}

.card{
background:var(--card);
padding:20px;
border-radius:15px;
border:1px solid var(--border);
box-shadow:0 5px 15px rgba(0,0,0,.35);
margin-bottom:20px;
}

/* TITLES */

h2{
margin-bottom:15px;
color:#fff;
}

h3{
margin-bottom:10px;
}

/* FORM */

input,
textarea,
select{
width:100%;
padding:14px;
margin-top:8px;
margin-bottom:12px;
background:#111;
border:1px solid #444;
border-radius:10px;
color:#fff;
font-size:15px;
outline:none;
transition:0.3s;
}

input:focus,
textarea:focus,
select:focus{
border-color:var(--primary);
box-shadow:0 0 10px rgba(255,0,0,.3);
}

textarea{
resize:vertical;
min-height:120px;
}

/* BUTTON */

button{
background:linear-gradient(135deg,#ff0000,#b30000);
color:#fff;
border:none;
padding:14px 20px;
border-radius:10px;
cursor:pointer;
font-size:15px;
font-weight:700;
transition:.3s;
}

button:hover{
transform:translateY(-2px);
box-shadow:0 8px 20px rgba(255,0,0,.4);
}

/* LOGIN */

.admin-login{
max-width:600px;
margin:30px auto;
}

.admin-panel{
animation:fadeIn .4s ease;
}

@keyframes fadeIn{
from{
opacity:0;
transform:translateY(20px);
}
to{
opacity:1;
transform:translateY(0);
}
}

/* STATS */

.stats{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:20px;
}

.stat-box{
background:linear-gradient(135deg,#1a1a1a,#2a0000);
padding:25px;
border-radius:15px;
border:1px solid #444;
text-align:center;
}

.stat-box h2{
font-size:2rem;
color:var(--primary);
}

/* PRODUCT GRID */

.product-grid{
display:grid;
grid-template-columns:repeat(auto-fill,minmax(280px,1fr));
gap:20px;
margin-top:20px;
}

/* PRODUCT CARD */

.product-card{
background:#1b1b1b;
border-radius:15px;
overflow:hidden;
border:1px solid #333;
transition:.3s;
}

.product-card:hover{
transform:translateY(-5px);
box-shadow:0 10px 25px rgba(255,0,0,.2);
}

.product-image{
width:100%;
height:240px;
object-fit:cover;
background:#000;
}

.product-content{
padding:15px;
}

.product-title{
font-size:18px;
font-weight:700;
margin-bottom:10px;
}

.product-price{
font-size:22px;
font-weight:800;
color:#00ff7f;
margin-bottom:10px;
}

.product-category{
display:inline-block;
background:#222;
padding:5px 12px;
border-radius:20px;
font-size:12px;
margin-bottom:10px;
}

.product-sku{
font-size:12px;
color:#aaa;
margin-bottom:8px;
}

.product-description{
font-size:14px;
color:#ddd;
margin-bottom:12px;
}

.product-days{
font-size:14px;
color:#ffcc00;
margin-bottom:15px;
}

/* PRODUCT ACTIONS */

.product-actions{
display:flex;
gap:10px;
flex-wrap:wrap;
}

.product-actions button{
flex:1;
min-width:100px;
}

/* CART */

.cart-section{
margin-top:30px;
}

.cart-item{
display:flex;
justify-content:space-between;
align-items:center;
background:#1a1a1a;
padding:15px;
border-radius:12px;
margin-bottom:10px;
border:1px solid #333;
}

.cart-left{
flex:1;
}

.cart-name{
font-weight:700;
}

.cart-price{
color:#00ff7f;
}

.cart-controls{
display:flex;
gap:8px;
align-items:center;
}

.qty-btn{
width:40px;
height:40px;
padding:0;
}

.cart-summary{
margin-top:20px;
background:#1a1a1a;
padding:20px;
border-radius:15px;
border:1px solid #444;
}

#cartTotal{
color:#00ff7f;
font-size:28px;
font-weight:800;
}

/* CHECKOUT */

.checkout-section{
margin-top:30px;
}

/* SHARE SECTION */

#shareSection{
max-width:700px;
margin:auto;
}

/* FOOTER */

footer{
margin-top:50px;
background:#000;
padding:40px 20px;
text-align:center;
border-top:3px solid var(--primary);
}

footer h2{
margin-bottom:10px;
}

footer p{
color:#aaa;
margin-top:5px;
}

/* SCROLLBAR */

::-webkit-scrollbar{
width:10px;
}

::-webkit-scrollbar-track{
background:#111;
}

::-webkit-scrollbar-thumb{
background:#b30000;
border-radius:10px;
}

/* MOBILE */

@media(max-width:768px){

.header{
flex-direction:column;
text-align:center;
gap:15px;
}

.header-right{
justify-content:center;
}

.product-grid{
grid-template-columns:1fr;
}

.cart-item{
flex-direction:column;
align-items:flex-start;
gap:15px;
}

.cart-controls{
width:100%;
justify-content:flex-start;
}

button{
width:100%;
}

}
</style></head>
<body><!-- HEADER --><header class="header"><div class="logo-area"><h1>SS DYNAMIC MARKETPLACE</h1><p>
Professional Marketplace Management System
</p></div><div class="header-right"><span id="productCounter">
Products : 0
</span><span id="cartCounter">
Cart : 0
</span></div></header><!-- ADMIN LOGIN --><section class="admin-login"><h2>ADMIN LOGIN</h2><div class="card"><input
type="text"
id="adminId"
placeholder="Admin ID">

<input
type="password"
id="adminPassword"
placeholder="Password">

<button onclick="loginAdmin()">
LOGIN
</button></div></section><!-- ADMIN PANEL --><section
class="admin-panel"
id="adminPanel"
style="display:none;"><div class="panel-header"><h2>
ADMIN DASHBOARD
</h2><button onclick="logoutAdmin()">
LOGOUT
</button></div><div class="card"><h3>
ADD NEW PRODUCT
</h3><input
type="text"
id="productName"
placeholder="Product Name">

<input
type="number"
id="productPrice"
placeholder="Price">

<input
type="text"
id="productCategory"
placeholder="Category">

<input
type="number"
id="productDays"
placeholder="Estimate Delivery Days">

<textarea
id="productDescription"
placeholder="Product Description">
</textarea><input
type="file"
id="productImage"
accept="image/*">

<button onclick="addProduct()">
ADD PRODUCT
</button></div></section><!-- MARKETPLACE STATS --><section class="stats"><div class="stat-box"><h3>Total Products</h3><h2 id="totalProducts">
0
</h2></div><div class="stat-box"><h3>Total Cart Items</h3><h2 id="totalCartItems">
0
</h2></div></section><!-- SEARCH --><section class="search-section"><div class="card"><h2>
SEARCH PRODUCTS
</h2><input
type="text"
id="searchInput"
placeholder="Search Product..."
onkeyup="searchProducts()">

<select
id="categoryFilter"
onchange="filterProducts()">

<option value="">
All Categories
</option></select></div></section><!-- PRODUCT LIST --><section class="product-section"><h2>
PRODUCT LISTINGS
</h2><div
id="productList"
class="product-grid"></div></section><!-- SHOPPING CART --><section class="cart-section"><h2>
SHOPPING CART
</h2><div
id="cartList"></div><div class="cart-summary"><h3>
TOTAL:
<span id="cartTotal">
RM0
</span>
</h3></div></section><!-- CUSTOMER ORDER FORM --><section class="checkout-section"><div class="card"><h2>
CUSTOMER ORDER FORM
</h2><input
type="text"
id="customerName"
placeholder="Customer Name">

<input
type="text"
id="customerWhatsapp"
placeholder="WhatsApp Number">

<input
type="email"
id="customerEmail"
placeholder="Email Address">

<textarea
id="customerAddress"
placeholder="Delivery Address">
</textarea><button onclick="sendOrderWhatsApp()">CHECKOUT VIA WHATSAPP

</button></div></section><!-- SHARE PRODUCT MODAL --><section
id="shareSection"
style="display:none;"><div class="card"><h2>
PRODUCT SHARE LINK
</h2><input
type="text"
id="shareLink"
readonly>

<button onclick="copyShareLink()">
COPY LINK
</button></div></section><!-- FOOTER --><footer><h2>
SS DYNAMIC MARKETPLACE
</h2><p>
Marketplace System Professional Edition
</p><p>
Powered By SS DYNAMIC
</p></footer><script>

/* =====================================
SS DYNAMIC MARKETPLACE PROFESSIONAL
PART 3A - CORE ENGINE
===================================== */

/* ADMIN CONFIG */

const ADMIN_ID = "SS DYNAMIC";
const ADMIN_PASSWORD = "#01234567890";

/* DATABASE */

let products =
JSON.parse(
localStorage.getItem("ssdynamic_products")
) || [];

let cart =
JSON.parse(
localStorage.getItem("ssdynamic_cart")
) || [];

/* INITIALIZE */

window.onload = function(){

renderProducts();

updateStatistics();

populateCategoryFilter();

};

/* =====================================
ADMIN LOGIN
===================================== */

function loginAdmin(){

const id =
document.getElementById("adminId").value.trim();

const password =
document.getElementById("adminPassword").value.trim();

if(
id === ADMIN_ID &&
password === ADMIN_PASSWORD
){

document.getElementById(
"adminPanel"
).style.display = "block";

alert("Admin Login Successful");

}else{

alert("Invalid Admin ID or Password");

}

}

/* =====================================
ADMIN LOGOUT
===================================== */

function logoutAdmin(){

document.getElementById(
"adminPanel"
).style.display = "none";

alert("Logout Successful");

}

/* =====================================
GENERATORS
===================================== */

function generateSKU(){

return "SKU-" +
Math.floor(
100000 + Math.random() * 900000
);

}

function generateProductID(){

return "PID-" +
Date.now();

}

function generateOrderID(){

return "ORD-" +
Date.now();

}

/* =====================================
SAVE DATABASE
===================================== */

function saveProducts(){

localStorage.setItem(
"ssdynamic_products",
JSON.stringify(products)
);

}

function saveCart(){

localStorage.setItem(
"ssdynamic_cart",
JSON.stringify(cart)
);

}

/* =====================================
ADD PRODUCT
===================================== */

function addProduct(){

const name =
document.getElementById("productName").value;

const price =
document.getElementById("productPrice").value;

const category =
document.getElementById("productCategory").value;

const days =
document.getElementById("productDays").value;

const description =
document.getElementById("productDescription").value;

const imageFile =
document.getElementById("productImage").files[0];

if(
!name ||
!price ||
!category ||
!description
){

alert(
"Please complete all product information"
);

return;

}

const reader =
new FileReader();

reader.onload = function(e){

const product = {

id:
generateProductID(),

sku:
generateSKU(),

name:
name,

price:
parseFloat(price),

category:
category,

days:
days,

description:
description,

image:
e.target.result,

created:
new Date().toLocaleString()

};

products.push(product);

saveProducts();

renderProducts();

updateStatistics();

populateCategoryFilter();

clearProductForm();

alert(
"Product Added Successfully"
);

};

if(imageFile){

reader.readAsDataURL(imageFile);

}else{

const product = {

id:
generateProductID(),

sku:
generateSKU(),

name:
name,

price:
parseFloat(price),

category:
category,

days:
days,

description:
description,

image:
"",

created:
new Date().toLocaleString()

};

products.push(product);

saveProducts();

renderProducts();

updateStatistics();

populateCategoryFilter();

clearProductForm();

alert(
"Product Added Successfully"
);

}

}

/* =====================================
DELETE PRODUCT
===================================== */

function deleteProduct(productId){

const confirmDelete =
confirm(
"Delete this product?"
);

if(!confirmDelete){

return;

}

products =
products.filter(
product =>
product.id !== productId
);

saveProducts();

renderProducts();

updateStatistics();

populateCategoryFilter();

}

/* =====================================
CLEAR PRODUCT FORM
===================================== */

function clearProductForm(){

document.getElementById(
"productName"
).value = "";

document.getElementById(
"productPrice"
).value = "";

document.getElementById(
"productCategory"
).value = "";

document.getElementById(
"productDays"
).value = "";

document.getElementById(
"productDescription"
).value = "";

document.getElementById(
"productImage"
).value = "";

}

/* =====================================
DASHBOARD STATISTICS
===================================== */

function updateStatistics(){

document.getElementById(
"totalProducts"
).innerText =
products.length;

document.getElementById(
"productCounter"
).innerText =
"Products : " +
products.length;

let totalCartQty = 0;

cart.forEach(item => {

totalCartQty += item.quantity;

});

document.getElementById(
"totalCartItems"
).innerText =
totalCartQty;

document.getElementById(
"cartCounter"
).innerText =
"Cart : " +
totalCartQty;

}

/* =====================================
CATEGORY FILTER
===================================== */

function populateCategoryFilter(){

const filter =
document.getElementById(
"categoryFilter"
);

if(!filter) return;

const currentValue =
filter.value;

filter.innerHTML =

'<option value="">All Categories</option>';

const categories =
[
...new Set(
products.map(
product =>
product.category
)
)
];

categories.forEach(category => {

const option =
document.createElement(
"option"
);

option.value =
category;

option.textContent =
category;

filter.appendChild(
option
);

});

filter.value =
currentValue;

}
/* =====================================
PART 3B
PRODUCT DISPLAY ENGINE
===================================== */

function renderProducts(filteredProducts = products){

const productList =
document.getElementById(
"productList"
);

if(!productList) return;

productList.innerHTML = "";

if(filteredProducts.length === 0){

productList.innerHTML = `

<div class="card"><h3>No Products Found</h3><p>
There are currently no products available.
</p></div>`;

return;

}

filteredProducts.forEach(product => {

const imageSource =

product.image && product.image !== ""

? product.image

: "https://via.placeholder.com/400x300?text=SS+DYNAMIC";

const productCard = `

<div class="product-card"><img
class="product-image"
src="${imageSource}"
alt="${product.name}">

<div class="product-content"><div class="product-sku">${product.sku}

</div><h3 class="product-title">${product.name}

</h3><div class="product-category">${product.category}

</div><div class="product-price">RM ${Number(product.price).toFixed(2)}

</div><div class="product-days">Estimated Delivery :
${product.days} Day(s)

</div><div class="product-description">${product.description}

</div><div class="product-actions"><button
onclick="addToCart('${product.id}')">

Add To Cart

</button><button
onclick="shareProduct('${product.id}')">

Share

</button><button
onclick="deleteProduct('${product.id}')">

Delete

</button></div></div></div>`;

productList.innerHTML +=
productCard;

});

}

/* =====================================
PRODUCT SEARCH
===================================== */

function searchProducts(){

const keyword =

document
.getElementById(
"searchInput"
)
.value
.toLowerCase()
.trim();

const results =

products.filter(product =>

product.name
.toLowerCase()
.includes(keyword)

||

product.category
.toLowerCase()
.includes(keyword)

||

product.description
.toLowerCase()
.includes(keyword)

||

product.sku
.toLowerCase()
.includes(keyword)

);

renderProducts(
results
);

}

/* =====================================
CATEGORY FILTER
===================================== */

function filterProducts(){

const category =

document
.getElementById(
"categoryFilter"
)
.value;

if(category === ""){

renderProducts(
products
);

return;

}

const filtered =

products.filter(product =>

product.category === category

);

renderProducts(
filtered
);

}

/* =====================================
PRODUCT SHARE LINK
===================================== */

function shareProduct(productId){

const product =

products.find(
item =>
item.id === productId
);

if(!product){

return;

}

const shareLink =

window.location.href
.split("?")[0]

+ 

"?product="

+ 

product.id;

document.getElementById(
"shareSection"
).style.display =
"block";

document.getElementById(
"shareLink"
).value =
shareLink;

window.scrollTo({

top:
document.getElementById(
"shareSection"
).offsetTop,

behavior:
"smooth"

});

}

/* =====================================
COPY SHARE LINK
===================================== */

function copyShareLink(){

const input =

document.getElementById(
"shareLink"
);

input.select();

input.setSelectionRange(
0,
99999
);

navigator.clipboard
.writeText(
input.value
);

alert(
"Product link copied successfully"
);

}

/* =====================================
PRODUCT SHARE AUTO OPEN
===================================== */

function openSharedProduct(){

const params =

new URLSearchParams(
window.location.search
);

const productId =

params.get(
"product"
);

if(!productId){

return;

}

const product =

products.find(
item =>
item.id === productId
);

if(!product){

return;

}

renderProducts(
[product]
);

}

openSharedProduct();

/* =====================================
REFRESH PRODUCT UI
===================================== */

function refreshMarketplace(){

renderProducts();

updateStatistics();

populateCategoryFilter();

}

/* =====================================
SORT PRODUCTS
===================================== */

function sortProductsLowHigh(){

const sorted =

[...products]

.sort(
(a,b)=>
a.price - b.price
);

renderProducts(
sorted
);

}

function sortProductsHighLow(){

const sorted =

[...products]

.sort(
(a,b)=>
b.price - a.price
);

renderProducts(
sorted
);

}

/* =====================================
NEWEST PRODUCTS
===================================== */

function sortNewestProducts(){

const sorted =

[...products]

.sort(
(a,b)=>

new Date(
b.created
)

- 

new Date(
a.created
)

);

renderProducts(
sorted
);

}

/* =====================================
TOTAL PRODUCT VALUE
===================================== */

function calculateInventoryValue(){

let total = 0;

products.forEach(product => {

total +=
Number(
product.price
);

});

return total.toFixed(2);

}

/* =====================================
DASHBOARD INVENTORY VALUE
===================================== */

function updateInventoryDisplay(){

const inventoryValue =

calculateInventoryValue();

console.log(

"Inventory Value RM",

inventoryValue

);

}

updateInventoryDisplay();
/* =====================================
PART 3C
SHOPPING CART ENGINE
===================================== */

/* =====================================
ADD TO CART
===================================== */

function addToCart(productId){

const product =

products.find(
item =>
item.id === productId
);

if(!product){

alert(
"Product not found"
);

return;

}

const existingItem =

cart.find(
item =>
item.id === productId
);

if(existingItem){

existingItem.quantity += 1;

}else{

cart.push({

id:
product.id,

sku:
product.sku,

name:
product.name,

price:
product.price,

image:
product.image,

quantity:
1

});

}

saveCart();

renderCart();

updateStatistics();

alert(
product.name +
" added to cart"
);

}

/* =====================================
RENDER CART
===================================== */

function renderCart(){

const cartList =

document.getElementById(
"cartList"
);

if(!cartList){

return;

}

cartList.innerHTML = "";

if(cart.length === 0){

cartList.innerHTML = `

<div class="card"><h3>
Shopping Cart Empty
</h3><p>
Please add products to cart.
</p></div>`;

document.getElementById(
"cartTotal"
).innerText =

"RM0.00";

updateStatistics();

return;

}

cart.forEach(item => {

const subtotal =

item.price *
item.quantity;

const imageSource =

item.image &&
item.image !== ""

? item.image

: "https://via.placeholder.com/120x120?text=SS+DYNAMIC";

cartList.innerHTML += `

<div class="cart-item"><div class="cart-left"><img
src="${imageSource}"
style="
width:80px;
height:80px;
object-fit:cover;
border-radius:10px;
margin-bottom:10px;
">

<div class="cart-name">${item.name}

</div><div class="cart-price">RM ${Number(item.price).toFixed(2)}

</div><div>SKU :
${item.sku}

</div><div>Subtotal :

RM ${subtotal.toFixed(2)}

</div></div><div class="cart-controls"><button
class="qty-btn"
onclick="decreaseQty('${item.id}')">

- 

</button><span>${item.quantity}

</span><button
class="qty-btn"
onclick="increaseQty('${item.id}')">

+ 

</button><button
onclick="removeCartItem('${item.id}')">

Remove

</button></div></div>`;

});

updateCartTotal();

updateStatistics();

}

/* =====================================
INCREASE QTY
===================================== */

function increaseQty(productId){

const item =

cart.find(
cartItem =>
cartItem.id === productId
);

if(!item){

return;

}

item.quantity += 1;

saveCart();

renderCart();

}

/* =====================================
DECREASE QTY
===================================== */

function decreaseQty(productId){

const item =

cart.find(
cartItem =>
cartItem.id === productId
);

if(!item){

return;

}

if(item.quantity > 1){

item.quantity -= 1;

}else{

removeCartItem(
productId
);

return;

}

saveCart();

renderCart();

}

/* =====================================
REMOVE CART ITEM
===================================== */

function removeCartItem(productId){

cart =

cart.filter(
item =>
item.id !== productId
);

saveCart();

renderCart();

updateStatistics();

}

/* =====================================
CLEAR CART
===================================== */

function clearCart(){

const confirmClear =

confirm(
"Clear entire cart?"
);

if(!confirmClear){

return;

}

cart = [];

saveCart();

renderCart();

updateStatistics();

alert(
"Cart cleared"
);

}

/* =====================================
CART TOTAL
===================================== */

function updateCartTotal(){

let total = 0;

cart.forEach(item => {

total +=

Number(item.price) *

Number(item.quantity);

});

document.getElementById(
"cartTotal"
).innerText =

"RM" +
total.toFixed(2);

}

/* =====================================
TOTAL CART ITEMS
===================================== */

function getTotalCartItems(){

let total = 0;

cart.forEach(item => {

total +=

Number(
item.quantity
);

});

return total;

}

/* =====================================
TOTAL CART VALUE
===================================== */

function getTotalCartValue(){

let total = 0;

cart.forEach(item => {

total +=

Number(item.price) *

Number(item.quantity);

});

return total;

}

/* =====================================
CART SUMMARY OBJECT
===================================== */

function getCartSummary(){

return {

items:
getTotalCartItems(),

total:
getTotalCartValue(),

products:
cart

};

}

/* =====================================
RESTORE CART
===================================== */

function restoreCart(){

renderCart();

updateStatistics();

}

/* =====================================
CART STORAGE CHECK
===================================== */

function initializeCart(){

if(

localStorage.getItem(
"ssdynamic_cart"
)

){

cart =

JSON.parse(

localStorage.getItem(
"ssdynamic_cart"
)

);

}

renderCart();

}

/* =====================================
QUICK BUY
===================================== */

function quickBuy(productId){

addToCart(
productId
);

window.scrollTo({

top:

document
.querySelector(
".cart-section"
)
.offsetTop,

behavior:
"smooth"

});

}

/* =====================================
CART EXPORT
===================================== */

function exportCartData(){

const data =

JSON.stringify(
cart,
null,
2
);

console.log(
data
);

return data;

}

/* =====================================
START CART
===================================== */

initializeCart();
/* =====================================
PART 3D
CHECKOUT & WHATSAPP ENGINE
===================================== */

/* =====================================
ORDER NUMBER GENERATOR
===================================== */

function generateOrderNumber(){

const randomNumber =

Math.floor(
1000 + Math.random() * 9000
);

return "SSD-" +
Date.now() +
"-" +
randomNumber;

}

/* =====================================
ORDER DATE
===================================== */

function getCurrentDateTime(){

return new Date()
.toLocaleString(
"en-MY"
);

}

/* =====================================
BUILD ORDER SUMMARY
===================================== */

function buildOrderSummary(){

let summary = "";

cart.forEach((item,index)=>{

const subtotal =

Number(item.price) *
Number(item.quantity);

summary +=

(index + 1) +

". " +

item.name +

"%0A" +

"SKU: " +

item.sku +

"%0A" +

"Qty: " +

item.quantity +

"%0A" +

"Price: RM" +

Number(item.price).toFixed(2) +

"%0A" +

"Subtotal: RM" +

subtotal.toFixed(2) +

"%0A%0A";

});

return summary;

}

/* =====================================
CUSTOMER VALIDATION
===================================== */

function validateCheckout(){

const customerName =

document.getElementById(
"customerName"
).value.trim();

const customerWhatsapp =

document.getElementById(
"customerWhatsapp"
).value.trim();

const customerEmail =

document.getElementById(
"customerEmail"
).value.trim();

const customerAddress =

document.getElementById(
"customerAddress"
).value.trim();

if(cart.length === 0){

alert(
"Shopping cart is empty"
);

return false;

}

if(customerName === ""){

alert(
"Customer name required"
);

return false;

}

if(customerWhatsapp === ""){

alert(
"WhatsApp number required"
);

return false;

}

if(customerEmail === ""){

alert(
"Email required"
);

return false;

}

if(customerAddress === ""){

alert(
"Address required"
);

return false;

}

return true;

}

/* =====================================
WHATSAPP CHECKOUT
===================================== */

function sendOrderWhatsApp(){

if(
!validateCheckout()
){

return;

}

const orderId =
generateOrderID();

const orderNumber =
generateOrderNumber();

const customerName =

document.getElementById(
"customerName"
).value;

const customerWhatsapp =

document.getElementById(
"customerWhatsapp"
).value;

const customerEmail =

document.getElementById(
"customerEmail"
).value;

const customerAddress =

document.getElementById(
"customerAddress"
).value;

const totalValue =

getTotalCartValue();

let message =

"🔥 SS DYNAMIC MARKETPLACE 🔥%0A%0A" +

"ORDER ID: " +
orderId +

"%0A" +

"ORDER NUMBER: " +
orderNumber +

"%0A" +

"DATE: " +
getCurrentDateTime() +

"%0A%0A" +

"====================%0A" +

"ORDER DETAILS%0A" +

"====================%0A%0A";

message +=
buildOrderSummary();

message +=

"====================%0A" +

"TOTAL ITEMS: " +

getTotalCartItems() +

"%0A" +

"TOTAL PRICE: RM" +

Number(totalValue)
.toFixed(2) +

"%0A" +

"====================%0A%0A" +

"CUSTOMER DETAILS%0A%0A" +

"NAME: " +
customerName +

"%0A" +

"WHATSAPP: " +
customerWhatsapp +

"%0A" +

"EMAIL: " +
customerEmail +

"%0A" +

"ADDRESS: " +
customerAddress +

"%0A%0A" +

"Thank You.";

window.open(

"https://wa.me/601151453147?text=" +

message,

"_blank"

);

alert(
"Redirecting to WhatsApp"
);

}

/* =====================================
ORDER CONFIRMATION
===================================== */

function confirmOrder(){

const confirmCheckout =

confirm(
"Confirm Order?"
);

if(
confirmCheckout
){

sendOrderWhatsApp();

}

}

/* =====================================
CLEAR CUSTOMER FORM
===================================== */

function clearCustomerForm(){

document.getElementById(
"customerName"
).value = "";

document.getElementById(
"customerWhatsapp"
).value = "";

document.getElementById(
"customerEmail"
).value = "";

document.getElementById(
"customerAddress"
).value = "";

}

/* =====================================
COMPLETE CHECKOUT
===================================== */

function completeCheckout(){

cart = [];

saveCart();

renderCart();

updateStatistics();

clearCustomerForm();

}

/* =====================================
MARKETPLACE INITIALIZER
===================================== */

function initializeMarketplace(){

renderProducts();

renderCart();

updateStatistics();

populateCategoryFilter();

}

/* =====================================
RESET MARKETPLACE
===================================== */

function resetMarketplace(){

const confirmReset =

confirm(
"Reset Marketplace?"
);

if(!confirmReset){

return;

}

localStorage.removeItem(
"ssdynamic_products"
);

localStorage.removeItem(
"ssdynamic_cart"
);

products = [];

cart = [];

initializeMarketplace();

alert(
"Marketplace Reset Complete"
);

}

/* =====================================
MARKETPLACE VERSION
===================================== */

const MARKETPLACE_VERSION =

"SS Dynamic Marketplace Professional v1.0";

console.log(
MARKETPLACE_VERSION
);

/* =====================================
START APPLICATION
===================================== */

initializeMarketplace();
</script></body>

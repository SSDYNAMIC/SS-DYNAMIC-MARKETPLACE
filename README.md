# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SS DYNAMIC MARKETPLACE</title>

<style>

body{
font-family:Arial,sans-serif;
margin:0;
background:#111;
color:#fff;
}

header{
background:#c00000;
padding:20px;
text-align:center;
}

.container{
width:95%;
max-width:1400px;
margin:auto;
padding:20px;
}

.card{
background:#1a1a1a;
padding:15px;
border-radius:10px;
margin-bottom:15px;
}

input,textarea,select{
width:100%;
padding:10px;
margin:5px 0;
border-radius:5px;
border:none;
}

button{
padding:10px 15px;
background:#c00000;
color:#fff;
border:none;
cursor:pointer;
}

.gallery{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:15px;
}

.product{
background:#222;
padding:10px;
border-radius:10px;
}

.product img{
width:100%;
height:250px;
object-fit:cover;
border-radius:10px;
}

</style>
</head>

<body>

<header>
<h1>SS DYNAMIC MARKETPLACE</h1>
<p>Buy Products Easily</p>
</header>

<div class="container">

<!-- ADMIN LOGIN -->
<div class="card">
<h2>Admin Login</h2>

<input type="text" id="adminID" placeholder="Admin ID">

<input type="password" id="adminPassword" placeholder="Password">

<button onclick="loginAdmin()">Login</button>
</div>

<!-- PRODUCT MANAGEMENT -->
<div class="card" id="adminPanel" style="display:none">

<h2>Product Management</h2>

<input type="file" id="productImage" multiple accept="image/*">

<input type="text" id="productName" placeholder="Product Name">

<input type="number" id="productPrice" placeholder="Price">

<input type="text" id="productCategory" placeholder="Category">

<input type="number" id="deliveryDay" placeholder="Estimate Delivery Days">

<textarea id="productDescription"
placeholder="Description"></textarea>

<button onclick="addProduct()">
Add Product
</button>

</div>

<!-- PRODUCT GALLERY -->
<h2>Product Gallery</h2>

<div id="gallery" class="gallery"></div>

<!-- SHOPPING CART -->
<div class="card">

<h2>Shopping Cart</h2>

<div id="cartItems"></div>

<h3 id="cartTotal">
Total: RM0
</h3>

</div>

<!-- ORDER FORM -->
<div class="card">

<h2>Order Form</h2>

<input type="text" id="customerName"
placeholder="Name">

<input type="text" id="customerWhatsapp"
placeholder="WhatsApp Number">

<input type="email" id="customerEmail"
placeholder="Email">

<textarea id="customerAddress"
placeholder="Address"></textarea>

<button onclick="checkoutWhatsapp()">
Order Via WhatsApp
</button>

</div>

</div>

<script>

let products =
JSON.parse(localStorage.getItem("products")) || [];

let cart=[];

function loginAdmin(){

let id =
document.getElementById("adminID").value;

let pass =
document.getElementById("adminPassword").value;

if(
id==="SS DYNAMIC" &&
pass==="#SSDYNAMIC303677"
){

document.getElementById("adminPanel")
.style.display="block";

alert("Admin Login Success");

}else{

alert("Invalid Login");

}

}

function generateSKU(){

return "SKU-" +
Date.now();

}

function generateOrderID(){

return "ORD-" +
Date.now();

}

function addProduct(){

let file =
document.getElementById("productImage").files[0];

if(!file) return;

let reader=new FileReader();

reader.onload=function(e){

let product={

id:Date.now(),

sku:generateSKU(),

image:e.target.result,

name:
document.getElementById("productName").value,

price:
document.getElementById("productPrice").value,

category:
document.getElementById("productCategory").value,

delivery:
document.getElementById("deliveryDay").value,

description:
document.getElementById("productDescription").value

};

products.push(product);

localStorage.setItem(
"products",
JSON.stringify(products)
);

renderProducts();

};

reader.readAsDataURL(file);

}

function renderProducts(){

let html="";

products.forEach((p,index)=>{

html+=`

<div class="product">

<img src="${p.image}">

<h3>${p.name}</h3>

<p>SKU : ${p.sku}</p>

<p>RM ${p.price}</p>

<p>${p.category}</p>

<p>${p.delivery} Days</p>

<p>${p.description}</p>

<button onclick="addCart(${index})">
Add Cart
</button>

<button onclick="deleteProduct(${index})">
Delete Product
</button>

</div>

`;

});

document.getElementById("gallery")
.innerHTML=html;

}

function deleteProduct(index){

products.splice(index,1);

localStorage.setItem(
"products",
JSON.stringify(products)
);

renderProducts();

}

function addCart(index){

cart.push(products[index]);

renderCart();

}

function renderCart(){

let total=0;
let html="";

cart.forEach((c,i)=>{

total+=Number(c.price);

html+=`

<p>
${c.name}
- RM${c.price}

<button onclick="removeCart(${i})">
Delete
</button>

</p>

`;

});

document.getElementById("cartItems")
.innerHTML=html;

document.getElementById("cartTotal")
.innerHTML=
"Total : RM"+total;

}

function removeCart(i){

cart.splice(i,1);

renderCart();

}

function checkoutWhatsapp(){

let orderID=
generateOrderID();

let name=
document.getElementById("customerName").value;

let phone=
document.getElementById("customerWhatsapp").value;

let address=
document.getElementById("customerAddress").value;

let email=
document.getElementById("customerEmail").value;

let message=
"SS DYNAMIC MARKETPLACE%0A"+
"Order ID : "+orderID+"%0A"+
"Name : "+name+"%0A"+
"Phone : "+phone+"%0A"+
"Email : "+email+"%0A"+
"Address : "+address+"%0A%0A";

cart.forEach(c=>{

message +=
c.name +
" - RM" +
c.price +
"%0A";

});

window.open(
"https://wa.me/601151453147?text="+message,
"_blank"
);

}

renderProducts();

</script>

</body>

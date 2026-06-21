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
background:#d60000;
padding:20px;
text-align:center;
}

.container{
max-width:1200px;
margin:auto;
padding:20px;
}

.login-box,
.admin-panel,
.shop-section,
.cart-section{
background:#1c1c1c;
padding:20px;
border-radius:10px;
margin-bottom:20px;
}

input,textarea,select{
width:100%;
padding:12px;
margin:5px 0;
border:none;
border-radius:5px;
}

button{
background:#d60000;
color:white;
border:none;
padding:12px;
cursor:pointer;
border-radius:5px;
}

button:hover{
background:#ff0000;
}

.product-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:20px;
}

.product{
background:#222;
padding:15px;
border-radius:10px;
}

.product img{
width:100%;
height:220px;
object-fit:cover;
border-radius:10px;
}

.hidden{
display:none;
}
</style>
</head>

<body>

<header>
<h1>SS DYNAMIC MARKETPLACE</h1>
<p>Professional Marketplace System</p>
</header>

<div class="container">

<div class="login-box">
<h2>Admin Login</h2>

<input type="text" id="adminid" placeholder="Admin ID">
<input type="password" id="password" placeholder="Password">

<button onclick="loginAdmin()">LOGIN</button>
</div>

<div id="adminPanel" class="admin-panel hidden">

<h2>Add Product</h2>

<input type="file" id="image">

<input type="text" id="name" placeholder="Product Name">

<input type="number" id="price" placeholder="Price">

<input type="text" id="category" placeholder="Category">

<input type="number" id="days" placeholder="Estimate Days">

<textarea id="description" placeholder="Description"></textarea>

<button onclick="addProduct()">ADD PRODUCT</button>

</div>

<div class="shop-section">

<h2>Product Gallery</h2>

<div id="gallery" class="product-grid"></div>

</div>

<div class="cart-section">

<h2>Shopping Cart</h2>

<div id="cart"></div>

<hr>

<h3>Customer Information</h3>

<input type="text" id="custName" placeholder="Name">
<input type="text" id="custWhatsapp" placeholder="WhatsApp Number">
<input type="email" id="custEmail" placeholder="Email">
<textarea id="custAddress" placeholder="Address"></textarea>

<button onclick="sendWhatsappOrder()">
ORDER VIA WHATSAPP
</button>

</div>

</div>

<script>

const ADMIN_ID = "SS DYNAMIC";
const ADMIN_PASS = "303677";

let products =
JSON.parse(localStorage.getItem("products")) || [];

let cart = [];

function loginAdmin(){

let id =
document.getElementById("adminid").value;

let pass =
document.getElementById("password").value;

if(id===ADMIN_ID && pass===ADMIN_PASS){

document.getElementById("adminPanel")
.classList.remove("hidden");

alert("Admin Login Success");

}else{
alert("Invalid Login");
}
}

function generateSKU(){
return "SKU-" + Date.now();
}

function generateOrderID(){
return "ORD-" + Math.floor(Math.random()*99999999);
}

function addProduct(){

let file =
document.getElementById("image").files[0];

if(!file){
alert("Upload Image");
return;
}

let reader = new FileReader();

reader.onload=function(){

let product = {

sku: generateSKU(),

name:
document.getElementById("name").value,

price:
document.getElementById("price").value,

category:
document.getElementById("category").value,

days:
document.getElementById("days").value,

description:
document.getElementById("description").value,

image: reader.result

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

let gallery =
document.getElementById("gallery");

gallery.innerHTML="";

products.forEach((p,index)=>{

gallery.innerHTML += `

<div class="product">

<img src="${p.image}">

<h3>${p.name}</h3>

<p>SKU: ${p.sku}</p>

<p>RM ${p.price}</p>

<p>${p.category}</p>

<p>${p.description}</p>

<p>Estimate ${p.days} Days</p>

<button onclick="addToCart(${index})">
Add To Cart
</button>

<button onclick="deleteProduct(${index})">
Delete
</button>

</div>

`;

});

}

function deleteProduct(index){

products.splice(index,1);

localStorage.setItem(
"products",
JSON.stringify(products)
);

renderProducts();

}

function addToCart(index){

cart.push(products[index]);

renderCart();

}

function renderCart(){

let div =
document.getElementById("cart");

div.innerHTML="";

cart.forEach((p,i)=>{

div.innerHTML += `
<p>
${p.name}
(RM ${p.price})
<button onclick="removeCart(${i})">
Delete
</button>
</p>
`;

});

}

function removeCart(i){

cart.splice(i,1);

renderCart();

}

function sendWhatsappOrder(){

let orderID = generateOrderID();

let customer =
document.getElementById("custName").value;

let phone =
document.getElementById("custWhatsapp").value;

let email =
document.getElementById("custEmail").value;

let address =
document.getElementById("custAddress").value;

let text =
"SS DYNAMIC MARKETPLACE%0A";

text += "Order ID: "+orderID+"%0A";
text += "Customer: "+customer+"%0A";
text += "Phone: "+phone+"%0A";
text += "Email: "+email+"%0A";
text += "Address: "+address+"%0A%0A";

cart.forEach(item=>{
text += item.name+" - RM"+item.price+"%0A";
});

window.open(
"https://wa.me/601151453147?text="+text,
"_blank"
);

}

renderProducts();

</script>

</body>

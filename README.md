# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">

<title>SS DYNAMIC MARKETPLACE</title>

<style>

body{
font-family:Arial,sans-serif;
margin:0;
background:#111;
color:white;
}

header{
background:#c00000;
padding:20px;
text-align:center;
font-size:30px;
font-weight:bold;
}

.container{
padding:20px;
max-width:1200px;
margin:auto;
}

.card{
background:#1b1b1b;
padding:15px;
margin-bottom:20px;
border-radius:10px;
}

input,textarea,select{
width:100%;
padding:10px;
margin-top:5px;
margin-bottom:10px;
border:none;
border-radius:5px;
}

button{
padding:10px 15px;
background:red;
color:white;
border:none;
cursor:pointer;
border-radius:5px;
}

button:hover{
background:#ff3333;
}

.grid{
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
height:220px;
object-fit:cover;
border-radius:10px;
}

.hidden{
display:none;
}

.cart-item{
padding:10px;
border-bottom:1px solid #333;
}

.badge{
background:red;
padding:5px 10px;
border-radius:20px;
}

</style>
</head>

<body>

<header>
SS DYNAMIC MARKETPLACE
</header>

<div class="container">

<div class="card">

<h2>Admin Login</h2>

<input id="adminid" placeholder="Admin ID">

<input id="adminpass" type="password" placeholder="Password">

<button onclick="loginAdmin()">Login</button>

</div>

<div id="adminPanel" class="card hidden">

<h2>Add Product</h2>

<input id="pname" placeholder="Product Name">

<input id="price" placeholder="Price">

<input id="category" placeholder="Category">

<input id="days" placeholder="Estimate Delivery Days">

<textarea id="description" placeholder="Description"></textarea>

<input type="file" id="image">

<button onclick="addProduct()">
Add Product
</button>

</div>

<div class="card">

<h2>
Products
</h2>

<div id="gallery" class="grid"></div>

</div>

<div class="card">

<h2>
Shopping Cart
<span id="cartcount" class="badge">0</span>
</h2>

<div id="cart"></div>

<h3 id="total">
Total: RM0
</h3>

</div>

<div class="card">

<h2>
Order Form
</h2>

<input id="custname" placeholder="Name">

<input id="custwa" placeholder="WhatsApp Number">

<input id="custemail" placeholder="Email">

<textarea id="custaddress" placeholder="Address"></textarea>

<button onclick="checkoutWhatsapp()">
Order Via WhatsApp
</button>

</div>

</div>

<script>

let products=
JSON.parse(localStorage.getItem("products"))||[];

let cart=[];

function loginAdmin(){

let id=
document.getElementById("adminid").value;

let pass=
document.getElementById("adminpass").value;

if(id==="SS DYNAMIC" && pass==="303677"){
document.getElementById("adminPanel").classList.remove("hidden");
alert("Admin Login Success");
}else{
alert("Invalid Login");
}

}

function generateSKU(){
return "SKU"+Date.now();
}

function addProduct(){

let file=
document.getElementById("image").files[0];

let reader=
new FileReader();

reader.onload=function(){

let product={
id:Date.now(),
sku:generateSKU(),
name:document.getElementById("pname").value,
price:document.getElementById("price").value,
category:document.getElementById("category").value,
days:document.getElementById("days").value,
description:document.getElementById("description").value,
image:reader.result
};

products.push(product);

localStorage.setItem(
"products",
JSON.stringify(products)
);

renderProducts();

};

if(file){
reader.readAsDataURL(file);
}

}

function renderProducts(){

let html="";

products.forEach(p=>{

html+=`

<div class="product">

<img src="${p.image}">

<h3>${p.name}</h3>

<p>SKU: ${p.sku}</p>

<p>RM ${p.price}</p>

<p>${p.category}</p>

<p>${p.description}</p>

<p>Estimate ${p.days} Days</p>

<button onclick="addCart(${p.id})">
Add Cart
</button>

<button onclick="deleteProduct(${p.id})">
Delete
</button>

</div>

`;

});

document.getElementById("gallery").innerHTML=html;

}

function deleteProduct(id){

products=
products.filter(p=>p.id!==id);

localStorage.setItem(
"products",
JSON.stringify(products)
);

renderProducts();

}

function addCart(id){

let item=
products.find(p=>p.id===id);

cart.push(item);

renderCart();

}

function renderCart(){

let html="";
let total=0;

cart.forEach((c,index)=>{

total+=Number(c.price);

html+=`

<div class="cart-item">

${c.name}
RM ${c.price}

<button onclick="removeCart(${index})">
X
</button>

</div>

`;

});

document.getElementById("cart").innerHTML=html;

document.getElementById("total").innerHTML=
"Total: RM"+total;

document.getElementById("cartcount").innerHTML=
cart.length;

}

function removeCart(i){

cart.splice(i,1);

renderCart();

}

function generateOrderID(){

return "ORD"+Date.now();

}

function checkoutWhatsapp(){

let orderid=
generateOrderID();

let name=
document.getElementById("custname").value;

let wa=
document.getElementById("custwa").value;

let email=
document.getElementById("custemail").value;

let address=
document.getElementById("custaddress").value;

let msg=
"SS DYNAMIC MARKETPLACE%0A"+
"Order ID: "+orderid+"%0A"+
"Name: "+name+"%0A"+
"WhatsApp: "+wa+"%0A"+
"Email: "+email+"%0A"+
"Address: "+address+"%0A%0A";

cart.forEach(c=>{
msg+=c.name+" RM"+c.price+"%0A";
});

window.open(
"https://wa.me/601151453147?text="+msg,
"_blank"
);

}

renderProducts();

</script>

</body>

# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<title>SS DYNAMIC MARKETPLACE</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
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
width:95%;
max-width:1400px;
margin:auto;
padding:20px;
}

.card{
background:#1b1b1b;
padding:20px;
border-radius:10px;
margin-bottom:20px;
border:1px solid #333;
}

input,select,textarea{
width:100%;
padding:12px;
margin-top:10px;
margin-bottom:10px;
border:none;
border-radius:6px;
}

button{
background:#c00000;
color:white;
padding:12px;
border:none;
border-radius:6px;
cursor:pointer;
width:100%;
font-weight:bold;
}

button:hover{
background:red;
}

.product-grid{
display:grid;
grid-template-columns:repeat(auto-fill,minmax(280px,1fr));
gap:20px;
}

.product{
background:#1b1b1b;
padding:15px;
border-radius:10px;
}

.product img{
width:100%;
height:220px;
object-fit:cover;
border-radius:10px;
}

.cart-item{
padding:10px;
border-bottom:1px solid #444;
}

.hidden{
display:none;
}

.admin-panel{
display:none;
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

<input type="text" id="adminid" placeholder="Admin ID">

<input type="password" id="adminpass" placeholder="Password">

<button onclick="loginAdmin()">
LOGIN
</button>

</div>

<div id="adminPanel" class="admin-panel">

<div class="card">

<h2>Add Product</h2>

<input type="text" id="productName" placeholder="Product Name">

<input type="number" id="productPrice" placeholder="Price">

<input type="text" id="productCategory" placeholder="Category">

<input type="text" id="estimateDay" placeholder="Estimate Delivery Day">

<input type="file" id="productImage">

<button onclick="addProduct()">
ADD PRODUCT
</button>

</div>

</div>

<div class="card">

<h2>Marketplace Products</h2>

<div id="productGrid" class="product-grid">

</div>

</div>

<div class="card">

<h2>Shopping Cart</h2>

<div id="cartItems">

</div>

<h3 id="totalPrice">
Total RM0
</h3>

</div>

<div class="card">

<h2>Customer Order Form</h2>

<input type="text" id="customerName" placeholder="Name">

<input type="text" id="customerWhatsapp" placeholder="WhatsApp Number">

<input type="email" id="customerEmail" placeholder="Email">

<textarea id="customerAddress" placeholder="Address"></textarea>

<button onclick="sendWhatsAppOrder()">
ORDER VIA WHATSAPP
</button>

</div>

</div>

<script>

let products=[];
let cart=[];

function loginAdmin(){

let id=document.getElementById("adminid").value;
let pass=document.getElementById("adminpass").value;

if(id==="SS DYNAMIC" && pass==="303677"){

document.getElementById("adminPanel").style.display="block";

alert("Admin Login Success");

}else{

alert("Invalid Login");

}

}

function generateSKU(){

return "SKU"+Date.now();

}

function generateOrderID(){

return "ORD"+Date.now();

}

function addProduct(){

let name=document.getElementById("productName").value;
let price=document.getElementById("productPrice").value;
let category=document.getElementById("productCategory").value;
let estimate=document.getElementById("estimateDay").value;

let file=document.getElementById("productImage").files[0];

if(!file) return;

let reader=new FileReader();

reader.onload=function(e){

let product={

id:Date.now(),

sku:generateSKU(),

name:name,

price:price,

category:category,

estimate:estimate,

image:e.target.result

};

products.push(product);

renderProducts();

};

reader.readAsDataURL(file);

}

function renderProducts(){

let html="";

products.forEach(product=>{

html+=`

<div class="product">

<img src="${product.image}">

<h3>${product.name}</h3>

<p>SKU : ${product.sku}</p>

<p>Category : ${product.category}</p>

<p>Estimate : ${product.estimate}</p>

<h2>RM ${product.price}</h2>

<button onclick="addToCart(${product.id})">

ADD TO CART

</button>

<button onclick="deleteProduct(${product.id})">

DELETE

</button>

</div>

`;

});

document.getElementById("productGrid").innerHTML=html;

}

function deleteProduct(id){

products=products.filter(x=>x.id!==id);

renderProducts();

}

function addToCart(id){

let item=products.find(x=>x.id===id);

cart.push(item);

renderCart();

}

function removeCart(index){

cart.splice(index,1);

renderCart();

}

function renderCart(){

let html="";
let total=0;

cart.forEach((item,index)=>{

total+=Number(item.price);

html+=`

<div class="cart-item">

${item.name}

- RM${item.price}

<button onclick="removeCart(${index})">

Remove

</button>

</div>

`;

});

document.getElementById("cartItems").innerHTML=html;
document.getElementById("totalPrice").innerHTML="Total RM"+total;

}

function sendWhatsAppOrder(){

let name=document.getElementById("customerName").value;
let phone=document.getElementById("customerWhatsapp").value;
let email=document.getElementById("customerEmail").value;
let address=document.getElementById("customerAddress").value;

let orderid=generateOrderID();

let order="";

cart.forEach(item=>{

order+=item.name+" - RM"+item.price+"%0A";

});

let msg=

"SS DYNAMIC MARKETPLACE ORDER%0A%0A"+

"Order ID: "+orderid+"%0A"+

"Name: "+name+"%0A"+

"Phone: "+phone+"%0A"+

"Email: "+email+"%0A"+

"Address: "+address+"%0A%0A"+

"ITEMS:%0A"+order;

window.open(

"https://wa.me/601151453147?text="+msg,

"_blank"

);

}

</script>

</body>

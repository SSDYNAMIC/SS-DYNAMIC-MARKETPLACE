# SS-DYNAMIC-MARKETPLACE
SS DYNAMIC FRIENDLY MARKETS PLACE
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0"><title>SS DYNAMIC MARKETPLACE</title><style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,Helvetica,sans-serif;
}

body{
background:#0f0f0f;
color:#ffffff;
}

header{
background:linear-gradient(135deg,#b30000,#000000);
padding:30px;
text-align:center;
border-bottom:3px solid red;
}

header h1{
font-size:40px;
color:white;
}

header p{
margin-top:10px;
color:#cccccc;
}

.container{
width:95%;
max-width:1400px;
margin:auto;
padding:20px;
}

.card{
background:#1a1a1a;
border:1px solid #333;
border-radius:10px;
padding:20px;
margin-bottom:20px;
}

h2{
color:red;
margin-bottom:15px;
}

input,
select,
textarea{
width:100%;
padding:12px;
margin-top:8px;
margin-bottom:15px;
border:none;
border-radius:8px;
background:#262626;
color:white;
}

button{
background:red;
color:white;
border:none;
padding:12px 20px;
border-radius:8px;
cursor:pointer;
font-weight:bold;
}

button:hover{
background:#cc0000;
}

.hidden{
display:none;
}

.login-box{
max-width:500px;
margin:40px auto;
}

.dashboard{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:20px;
}

.stat-box{
background:#1f1f1f;
padding:20px;
border-radius:10px;
text-align:center;
border:1px solid #444;
}

.stat-box h3{
font-size:32px;
color:red;
}

.product-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:20px;
}

.product-card{
background:#1c1c1c;
border-radius:10px;
overflow:hidden;
border:1px solid #333;
}

.product-card img{
width:100%;
height:220px;
object-fit:cover;
}

.product-info{
padding:15px;
}

.product-info h3{
margin-bottom:10px;
}

.product-price{
font-size:22px;
color:red;
font-weight:bold;
margin-bottom:10px;
}

.admin-panel{
border:2px solid red;
}

.cart-btn{
width:100%;
margin-top:10px;
}

.whatsapp-btn{
background:#25D366;
}

.whatsapp-btn:hover{
background:#128C7E;
}

.logout-btn{
background:#444;
margin-left:10px;
}

.logout-btn:hover{
background:#666;
}

table{
width:100%;
border-collapse:collapse;
}

table th,
table td{
border:1px solid #444;
padding:10px;
text-align:left;
}

table th{
background:red;
}

footer{
background:black;
padding:20px;
text-align:center;
margin-top:50px;
}

@media(max-width:768px){

header h1{
font-size:28px;
}

.dashboard{
grid-template-columns:1fr;
}

}

</style></head><body><header><h1>SS DYNAMIC MARKETPLACE</h1><p>
Sale Product Pages Responsibility To Customer
</p><p>
</p></header><div class="container"><!-- LOGIN SECTION --><div id="loginSection" class="card login-box"><h2>Admin Login</h2><input
type="text"
id="adminId"
placeholder="Admin ID">

<input
type="password"
id="adminPassword"
placeholder="Password">

<button onclick="adminLogin()">
LOGIN
</button></div><!-- ADMIN PANEL --><div
id="adminPanel"
class="card admin-panel hidden"><h2>Admin Dashboard</h2><button onclick="logoutAdmin()" class="logout-btn">
Logout
</button><br><br>

<div class="dashboard"><div class="stat-box">
<h3 id="totalProducts">0</h3>
<p>Total Products</p>
</div><div class="stat-box">
<h3 id="totalOrders">0</h3>
<p>Total Orders</p>
</div><div class="stat-box">
<h3 id="totalRevenue">RM0</h3>
<p>Total Revenue</p>
</div></div><br><h2>Add Product</h2><input
type="text"
id="productName"
placeholder="Product Name">

<input
type="text"
id="productCategory"
placeholder="Category">

<input
type="number"
id="productPrice"
placeholder="Price">

<input
type="number"
id="deliveryDays"
placeholder="Estimated Delivery Days">

<textarea
id="productDescription"
placeholder="Description">
</textarea><input
type="file"
id="productImage"
accept="image/*">

<button onclick="addProduct()">
Add Product
</button></div><!-- PRODUCT LISTING --><div class="card"><h2>Product Listing</h2><div
id="productContainer"
class="product-grid"><!-- AUTO GENERATED PRODUCTS --></div></div><!-- SHOPPING CART --><div class="card"><h2>Shopping Cart</h2><div id="cartContainer"><p>No Product Added.</p></div><br><h3>
Total:
RM <span id="cartTotal">0</span>
</h3></div><!-- CUSTOMER ORDER FORM --><div class="card"><h2>Customer Order Form</h2><input
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
class="whatsapp-btn"
onclick="checkoutWhatsapp()">

Send Order To WhatsApp

</button></div><footer><h3>SS DYNAMIC MARKETPLACE</h3><p>
Powered By SS DYNAMIC
</p></footer><script>

/* PART 1 VARIABLES */

const ADMIN_ID = "SS DYNAMIC";
const ADMIN_PASSWORD = "#SSDYNAMIC303677";

let products = [];
let cart = [];
let orders = [];

/* =========================
LOCAL STORAGE LOADING
========================= */

if(localStorage.getItem("ss_products")){
products = JSON.parse(localStorage.getItem("ss_products"));
}

if(localStorage.getItem("ss_cart")){
cart = JSON.parse(localStorage.getItem("ss_cart"));
}

if(localStorage.getItem("ss_orders")){
orders = JSON.parse(localStorage.getItem("ss_orders"));
}

if(sessionStorage.getItem("ss_admin_login") === "true"){
document.getElementById("loginSection").classList.add("hidden");
document.getElementById("adminPanel").classList.remove("hidden");
}

/* =========================
SAVE FUNCTIONS
========================= */

function saveProducts(){
localStorage.setItem(
"ss_products",
JSON.stringify(products)
);
}

function saveCart(){
localStorage.setItem(
"ss_cart",
JSON.stringify(cart)
);
}

function saveOrders(){
localStorage.setItem(
"ss_orders",
JSON.stringify(orders)
);
}

/* =========================
ADMIN LOGIN
========================= */

function adminLogin(){

const id =
document.getElementById("adminId").value.trim();

const password =
document.getElementById("adminPassword").value;

if(
    id === ADMIN_ID &&
    password === ADMIN_PASSWORD
){

    sessionStorage.setItem(
        "ss_admin_login",
        "true"
    );

    document
    .getElementById("loginSection")
    .classList.add("hidden");

    document
    .getElementById("adminPanel")
    .classList.remove("hidden");

    alert("Admin Login Successful");

}else{

    alert("Invalid Admin Login");

}

}

/* =========================
LOGOUT
========================= */

function logoutAdmin(){

sessionStorage.removeItem(
    "ss_admin_login"
);

location.reload();

}

/* =========================
SKU GENERATOR
========================= */

function generateSKU(){

let nextNumber =
products.length + 1001;

return "SSD-" + nextNumber;

}

/* =========================
ORDER ID GENERATOR
========================= */

function generateOrderID(){

let nextOrder =
orders.length + 1;

return "ORD-" +
String(nextOrder)
.padStart(6,"0");

}

/* =========================
ADD PRODUCT
========================= */

function addProduct(){

const name =
document.getElementById("productName").value;

const category =
document.getElementById("productCategory").value;

const price =
document.getElementById("productPrice").value;

const days =
document.getElementById("deliveryDays").value;

const description =
document.getElementById("productDescription").value;

const imageFile =
document.getElementById("productImage").files[0];

if(
    !name ||
    !category ||
    !price
){
    alert(
        "Please Complete Product Information"
    );
    return;
}

const sku =
generateSKU();

if(imageFile){

    const reader =
    new FileReader();

    reader.onload =
    function(e){

        const product = {

            sku: sku,

            name: name,

            category: category,

            price: price,

            deliveryDays: days,

            description: description,

            image:
            e.target.result

        };

        products.push(product);

        saveProducts();

        renderProducts();

        updateDashboard();

        clearProductForm();

    };

    reader.readAsDataURL(imageFile);

}else{

    const product = {

        sku: sku,

        name: name,

        category: category,

        price: price,

        deliveryDays: days,

        description: description,

        image:
        "https://via.placeholder.com/600x400?text=SS+DYNAMIC"

    };

    products.push(product);

    saveProducts();

    renderProducts();

    updateDashboard();

    clearProductForm();

}

}

/* =========================
CLEAR PRODUCT FORM
========================= */

function clearProductForm(){

document.getElementById("productName").value="";
document.getElementById("productCategory").value="";
document.getElementById("productPrice").value="";
document.getElementById("deliveryDays").value="";
document.getElementById("productDescription").value="";
document.getElementById("productImage").value="";

}

/* =========================
DELETE PRODUCT
========================= */

function deleteProduct(index){

if(
    !confirm(
        "Delete Product?"
    )
){
    return;
}

products.splice(index,1);

saveProducts();

renderProducts();

updateDashboard();

}

/* =========================
PRODUCT LISTING
========================= */

function renderProducts(){

const container =
document.getElementById(
    "productContainer"
);

container.innerHTML = "";

products.forEach(
(product,index)=>{

    const isAdmin =
    sessionStorage.getItem(
        "ss_admin_login"
    ) === "true";

    let adminButtons = "";

    if(isAdmin){

        adminButtons =
        `
        <button
        onclick="deleteProduct(${index})">
        Delete Product
        </button>
        `;

    }

    container.innerHTML +=

    `
    <div class="product-card">

        <img
        src="${product.image}">

        <div class="product-info">

            <h3>
            ${product.name}
            </h3>

            <p>
            SKU:
            ${product.sku}
            </p>

            <p>
            Category:
            ${product.category}
            </p>

            <div
            class="product-price">

            RM ${product.price}

            </div>

            <p>
            ${product.description}
            </p>

            <p>
            ETA:
            ${product.deliveryDays}
            Day(s)
            </p>

            <button
            class="cart-btn"
            onclick="addToCart(${index})">

            Add To Cart

            </button>

            ${adminButtons}

        </div>

    </div>
    `;

});

}

/* =========================
DASHBOARD
========================= */

function updateDashboard(){

document.getElementById(
    "totalProducts"
).innerText =
products.length;

document.getElementById(
    "totalOrders"
).innerText =
orders.length;

}/* =========================
ADD TO CART
========================= */

function addToCart(index){

const product = products[index];

const existingItem =
cart.find(
    item =>
    item.sku === product.sku
);

if(existingItem){

    existingItem.qty++;

}else{

    cart.push({

        sku: product.sku,

        name: product.name,

        price: Number(product.price),

        qty: 1

    });

}

saveCart();

renderCart();

}

/* =========================
REMOVE CART ITEM
========================= */

function removeCartItem(index){

cart.splice(index,1);

saveCart();

renderCart();

}

/* =========================
UPDATE CART
========================= */

function renderCart(){

const container =
document.getElementById(
    "cartContainer"
);

if(cart.length === 0){

    container.innerHTML =
    "<p>No Product Added.</p>";

    document.getElementById(
        "cartTotal"
    ).innerText = "0";

    return;

}

let html = "";

let total = 0;

cart.forEach(
(item,index)=>{

    const subtotal =
    item.price * item.qty;

    total += subtotal;

    html +=

    `
    <div class="card">

        <h3>
        ${item.name}
        </h3>

        <p>
        SKU:
        ${item.sku}
        </p>

        <p>
        Quantity:
        ${item.qty}
        </p>

        <p>
        RM ${item.price}
        </p>

        <p>
        Subtotal:
        RM ${subtotal}
        </p>

        <button
        onclick="removeCartItem(${index})">

        Remove

        </button>

    </div>
    `;

});

container.innerHTML = html;

document.getElementById(
    "cartTotal"
).innerText = total;

}

/* =========================
CALCULATE CART TOTAL
========================= */

function calculateCartTotal(){

let total = 0;

cart.forEach(item=>{

    total +=
    item.price * item.qty;

});

return total;

}

/* =========================
CHECKOUT WHATSAPP
========================= */

function checkoutWhatsapp(){

if(cart.length === 0){

    alert(
        "Shopping Cart Empty"
    );

    return;

}

const name =
document.getElementById(
    "customerName"
).value;

const whatsapp =
document.getElementById(
    "customerWhatsapp"
).value;

const email =
document.getElementById(
    "customerEmail"
).value;

const address =
document.getElementById(
    "customerAddress"
).value;

if(
    !name ||
    !whatsapp ||
    !address
){

    alert(
        "Please Complete Customer Information"
    );

    return;

}

const orderID =
generateOrderID();

let total =
calculateCartTotal();

let productList = "";

cart.forEach(item=>{

    productList +=

    "• " +
    item.name +
    " | Qty: " +
    item.qty +
    " | RM " +
    (
        item.price *
        item.qty
    ) +
    "\n";

});

const order = {

    orderID:
    orderID,

    customer:
    name,

    whatsapp:
    whatsapp,

    email:
    email,

    address:
    address,

    total:
    total,

    date:
    new Date()
    .toLocaleString()

};

orders.push(order);

saveOrders();

const message =

`SS DYNAMIC MARKETPLACE

ORDER ID:
${orderID}

CUSTOMER:
${name}

WHATSAPP:
${whatsapp}

EMAIL:
${email}

ADDRESS:
${address}

---

PRODUCTS

${productList}

---

TOTAL:
RM ${total}

Thank You`;

const encodedMessage =
encodeURIComponent(
    message
);

window.open(
"https://wa.me/601151453147?text=" +
encodedMessage,
"_blank"
);

cart = [];

saveCart();

renderCart();

updateDashboard();

updateRevenue();

alert(
    "Order Created Successfully"
);

}

/* =========================
REVENUE
========================= */

function updateRevenue(){

let revenue = 0;

orders.forEach(order=>{

    revenue +=
    Number(order.total);

});

document.getElementById(
    "totalRevenue"
).innerText =
"RM " + revenue;

}

/* =========================
LOAD ALL DATA
========================= */

function initializeSystem(){

renderProducts();

renderCart();

updateDashboard();

updateRevenue();

}

initializeSystem();

/* =========================
ENTER KEY LOGIN
========================= */

document
.getElementById(
"adminPassword"
)
.addEventListener(
"keypress",
function(e){

if(e.key==="Enter"){

adminLogin();

}

}
);

/* =========================
AUTO REFRESH DASHBOARD
========================= */

setInterval(()=>{

updateDashboard();

updateRevenue();

},3000);

/* =========================
END SYSTEM
========================= */
</script>

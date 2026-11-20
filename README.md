<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PetCare - Smart Pet Care</title>
<style>
*{box-sizing:border-box;scroll-behavior:smooth}
body{margin:0;font-family:Arial,sans-serif;background:#fff0df;color:#333}
.header{background:#df624f;color:white;text-align:center;padding:20px}
.header h1{margin:0;font-size:32px}
.navbar{background:#c95748;text-align:center;padding:10px;position:sticky;top:0;z-index:10}
.navbar button{background:transparent;color:white;border:0;padding:12px;font-weight:bold;cursor:pointer;border-radius:5px}
.navbar button:hover,.navbar button.active{background:#fff0df;color:#c95748}
.page{display:none;padding:30px 6%;min-height:65vh}.page.active{display:block}
h2{color:#c95748}
button.action{background:#df624f;color:white;border:0;padding:11px 18px;border-radius:5px;cursor:pointer;margin:8px 5px 0 0}
button.action:hover{background:#a94335}
.hero{padding:30px 0}.hero h2{font-size:38px}
.hero-image{width:100%;max-width:650px;height:300px;object-fit:cover;border-radius:15px}
.care-box,.checklist,.cart,.saved-profile{background:white;padding:20px;margin:15px 0;border-radius:10px}
.container{max-width:900px;margin:auto}
.form-box{background:#f1f6f7;padding:25px;border-radius:10px}
label{display:block;font-weight:bold;margin-top:12px}
input,select,textarea{width:100%;padding:12px;margin:7px 0 12px;border:1px solid #ccc;border-radius:5px}
textarea{height:100px}
table{width:100%;border-collapse:collapse;background:white}
th,td{padding:12px;border-bottom:1px solid #ddd;text-align:left}th{background:#e7b5a8}
.checklist label{font-weight:normal}.checklist input{width:auto}
.shop-heading{text-align:center;padding:15px}
.shop-banner{width:100%;max-height:300px;object-fit:cover;border-radius:15px;margin-bottom:20px}
.products{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:20px;margin:20px 0 35px}
.product{background:white;padding:12px;text-align:center;border-radius:12px;box-shadow:0 3px 8px #ddd;transition:.3s}
.product:hover{transform:translateY(-5px)}
.product img{width:100%;height:165px;object-fit:cover;background:#f8f5f3;border-radius:8px}
.product h3{color:#c95748;min-height:22px}.price{font-weight:bold;font-size:19px}
.category-title{background:#df806b;color:white;padding:12px;border-radius:8px}
.cart{box-shadow:0 3px 8px #ddd;margin-top:30px}
.cart-item{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px;border-bottom:1px solid #ddd;padding:12px 0}
.cart-item img{width:65px;height:65px;object-fit:cover;background:#f8f5f3;border-radius:6px}
.cart-product{display:flex;align-items:center;gap:12px}
.cart-item button{background:#df624f;color:white;border:0;padding:7px 12px;border-radius:5px;cursor:pointer}
.total{text-align:right;font-size:23px;font-weight:bold;color:#c95748;margin-top:20px}
footer{background:#c95748;color:white;text-align:center;padding:18px}
.profile-details{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:10px}
.profile-details p{margin:7px 0}.muted{color:#666}
@media(max-width:600px){.navbar{position:static}.navbar button{padding:8px;font-size:12px}.hero h2{font-size:30px}.page{padding:20px 5%}th,td{padding:7px;font-size:12px}.cart-item{font-size:13px}}
</style>
</head>
<body>
<div class="header"><h1> 🐾 CUDDLE'S PET CARE 🐾</h1><p>Smart Pet Care for Busy Owners</p></div>
<nav class="navbar">
<button class="active" onclick="showPage('home',this)">🏠 Home</button>
<button onclick="showPage('profile',this)">🐾 Pet Profile</button>
<button onclick="showPage('daily',this)">📋 Daily Care</button>
<button onclick="showPage('shop',this)">🛍️ Pet Shop</button>
<button onclick="showPage('contact',this)">✉️ Contact</button>
</nav>

<section id="home" class="page active">
<div class="hero">
<h2>Smart Pet Care for Busy Owners</h2>
<img class="hero-image" src="https://images.unsplash.com/photo-1450778869180-41d0601e046e?auto=format&fit=crop&w=1200&q=85" alt="Happy dog and cat">
<p>Busy pet owners often find it difficult to remember feeding times, walks, medication and health appointments. PetCare helps organize all daily pet responsibilities in one place.</p>
<button class="action" onclick="showPage('shop')">Explore Pet Shop</button>
</div>
<h2>Why PetCare?</h2>
<div class="care-box"><h3>🍲 Feeding</h3><p>Keep track of your pet's daily meal schedule.</p></div>
<div class="care-box"><h3>🐕 Exercise</h3><p>Organize daily walks and exercise activities.</p></div>
<div class="care-box"><h3>🩺 Health</h3><p>Keep vaccination and health information organized.</p></div>
<div class="care-box"><h3>⏰ Reminders</h3><p>Make daily pet-care responsibilities easier to remember.</p></div>
</section>

<section id="profile" class="page"><div class="container">
<h2>🐾 Create Your Pet Profile</h2><p>Enter your pet's basic information. Your saved profile will appear below and remain saved in this browser.</p>
<div class="form-box">
<form id="profileForm">
<label for="petName">Pet Name:</label><input type="text" id="petName" required>
<label for="breed">Breed:</label><input type="text" id="breed" required>
<label for="age">Age (years):</label><input type="number" id="age" min="0" step="any" required>
<label for="weight">Weight (kg):</label><input type="number" id="weight" min="0" step="any" required>
<label for="petType">Pet Type:</label><select id="petType"><option>Dog</option><option>Cat</option><option>Bird</option><option>Other</option></select>
<label for="info">Additional Information:</label><textarea id="info" placeholder="Favourite food, allergies, care notes, etc."></textarea>
<button class="action" type="submit">Save / Update Profile</button>
<button class="action" type="button" onclick="resetProfileForm()">Clear Form</button>
</form>
<p id="profileMessage" role="status" aria-live="polite"></p>
</div>
<div id="savedProfile" class="saved-profile"><h2>Saved Pet Profile</h2><p class="muted">No pet profile saved yet. Fill in the form and select Save Profile.</p></div>
</div></section>

<section id="daily" class="page">
<h2>📋 Daily Pet Care</h2><p>A simple schedule helps you remember important activities.</p><h3>Example Daily Pet Routine</h3>
<table><tr><th>Time</th><th>Activity</th><th>Description</th></tr>
<tr><td>7:00 AM</td><td>Breakfast</td><td>Give morning food</td></tr><tr><td>8:00 AM</td><td>Walk</td><td>Morning exercise</td></tr><tr><td>1:00 PM</td><td>Water</td><td>Check fresh water</td></tr><tr><td>6:00 PM</td><td>Dinner</td><td>Give evening food</td></tr><tr><td>7:00 PM</td><td>Walk</td><td>Evening exercise</td></tr><tr><td>9:00 PM</td><td>Medication</td><td>If prescribed</td></tr></table>
<div class="checklist"><h2>Daily Care Checklist</h2>
<label><input type="checkbox"> Give fresh drinking water.</label><label><input type="checkbox"> Provide morning food.</label><label><input type="checkbox"> Take pet for a walk.</label><label><input type="checkbox"> Check pet's condition.</label><label><input type="checkbox"> Provide evening food.</label><label><input type="checkbox"> Complete medication if required.</label></div>
</section>

<section id="shop" class="page">
<div class="shop-heading"><h2>🛍️ Pet Food & Accessories</h2><p>Everything your lovely pet needs in one place!</p>
<img class="shop-banner" src="https://images.unsplash.com/photo-1583337130417-3346a1be7dee?auto=format&fit=crop&w=1200&q=85" alt="Pets and pet supplies"></div>
<h2 class="category-title">🍲 Pet Food</h2><div class="products" id="foodProducts"></div>
<h2 class="category-title">🧸 Pet Accessories</h2><div class="products" id="accessoryProducts"></div>
<div class="cart"><h2>🛒 Your Shopping Cart</h2><p id="cartCount">Items: 0</p><div id="cartItems">Your cart is empty!</div>
<div class="total">Total: ₹<span id="total">0</span></div>
<button class="action" onclick="clearCart()">Clear Cart</button><button class="action" onclick="checkout()">Checkout</button></div>
</section>

<section id="contact" class="page"><div class="container"><h2>✉️ Contact & Feedback</h2><p>Have a suggestion to make pet care easier? Send us your feedback.</p>
<div class="form-box"><form id="feedbackForm"><label for="userName">Your Name:</label><input type="text" id="userName" required>
<label for="email">Email:</label><input type="email" id="email" required><label for="message">Your Message:</label><textarea id="message" required></textarea>
<button class="action" type="submit">Send Feedback</button></form></div></div></section>
<footer><p>🐾 PetCare - Love, Care & Happiness for Every Pet</p><p>Thank you for visiting PetCare!</p></footer>

<script>
function showPage(id,button){
 document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 document.querySelectorAll(".navbar button").forEach(b=>b.classList.remove("active"));
 if(button) button.classList.add("active");
 else document.querySelectorAll(".navbar button").forEach(b=>{if(b.getAttribute("onclick")?.includes("'" + id + "'"))b.classList.add("active")});
 window.scrollTo(0,0);
}

/* PET PROFILE: save, load and display all saved fields */
const PROFILE_KEY="petProfile";
function getSavedProfile(){
 try{return JSON.parse(localStorage.getItem(PROFILE_KEY));}
 catch(error){console.error("Could not read saved profile:",error);return null;}
}
function renderProfile(){
 const p=getSavedProfile(), area=document.getElementById("savedProfile");
 area.innerHTML="";
 const heading=document.createElement("h2");heading.textContent="🐾 Saved Pet Profile";area.appendChild(heading);
 if(!p){const msg=document.createElement("p");msg.className="muted";msg.textContent="No pet profile saved yet. Fill in the form and select Save / Update Profile.";area.appendChild(msg);return;}
 const details=document.createElement("div");details.className="profile-details";
 const fields=[["Pet Name",p.name],["Breed",p.breed],["Age",p.age+" years"],["Weight",p.weight+" kg"],["Pet Type",p.type],["Additional Information",p.info||"Not provided"]];
 fields.forEach(([label,value])=>{const item=document.createElement("p");const strong=document.createElement("strong");strong.textContent=label+": ";item.append(strong,document.createTextNode(value));details.appendChild(item);});
 area.appendChild(details);
 const note=document.createElement("p");note.className="muted";note.textContent="This information is saved in this browser on this device.";area.appendChild(note);
 const edit=document.createElement("button");edit.className="action";edit.textContent="Edit Profile";edit.onclick=()=>{document.getElementById("petName").value=p.name;document.getElementById("breed").value=p.breed;document.getElementById("age").value=p.age;document.getElementById("weight").value=p.weight;document.getElementById("petType").value=p.type;document.getElementById("info").value=p.info||"";document.getElementById("petName").focus();};area.appendChild(edit);
 const del=document.createElement("button");del.className="action";del.textContent="Delete Profile";del.onclick=()=>{if(confirm("Delete the saved pet profile?")){localStorage.removeItem(PROFILE_KEY);document.getElementById("profileForm").reset();renderProfile();document.getElementById("profileMessage").textContent="Saved profile deleted.";}};area.appendChild(del);
}
document.getElementById("profileForm").addEventListener("submit",function(e){
 e.preventDefault();
 const p={name:document.getElementById("petName").value.trim(),breed:document.getElementById("breed").value.trim(),age:document.getElementById("age").value,weight:document.getElementById("weight").value,type:document.getElementById("petType").value,info:document.getElementById("info").value.trim()};
 try{localStorage.setItem(PROFILE_KEY,JSON.stringify(p));renderProfile();document.getElementById("profileMessage").textContent="✅ Profile saved successfully! Your details are shown below."; }
 catch(error){document.getElementById("profileMessage").textContent="Unable to save the profile. Please check your browser storage settings.";console.error(error);}
});
function resetProfileForm(){document.getElementById("profileForm").reset();document.getElementById("profileMessage").textContent="Form cleared. Your previously saved profile has not been deleted.";}
renderProfile();

/* Product photos: individual image URLs selected to match each product */
const products=[
{id:1,name:"Dog Food",price:450,category:"food",image:"https://images.unsplash.com/photo-1589924691995-400dc9ecc119?auto=format&fit=crop&w=800&q=85"},
{id:2,name:"Cat Food",price:350,category:"food",image:"https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=800&q=85"},
{id:3,name:"Dog Treats",price:180,category:"food",image:"https://images.unsplash.com/photo-1582798358481-d199fb7347bb?auto=format&fit=crop&w=800&q=85"},
{id:4,name:"Pet Biscuits",price:120,category:"food",image:"https://images.unsplash.com/photo-1582798358481-d199fb7347bb?auto=format&fit=crop&w=800&q=85"},
{id:5,name:"Pet Toy",price:200,category:"accessory",image:"https://images.unsplash.com/photo-1535294435445-d7249524ef2e?auto=format&fit=crop&w=800&q=85"},
{id:6,name:"Pet Collar",price:250,category:"accessory",image:"https://images.unsplash.com/photo-1551717743-49959800b1f6?auto=format&fit=crop&w=800&q=85"},
{id:7,name:"Pet Bed",price:850,category:"accessory",image:"https://images.unsplash.com/photo-1541599540903-216a46ca1dc0?auto=format&fit=crop&w=800&q=85"},
{id:8,name:"Grooming Brush",price:150,category:"accessory",image:"https://images.unsplash.com/photo-1516734212186-a967f81ad0d7?auto=format&fit=crop&w=800&q=85"},
{id:9,name:"Water Bowl",price:180,category:"accessory",image:"https://images.unsplash.com/photo-1589924691995-400dc9ecc119?auto=format&fit=crop&w=800&q=85"},
{id:10,name:"Pet Shampoo",price:220,category:"accessory",image:"https://images.unsplash.com/photo-1601758228041-f3b2795255f1?auto=format&fit=crop&w=800&q=85"}
];
function displayProducts(){
 const food=document.getElementById("foodProducts"),accessories=document.getElementById("accessoryProducts");food.innerHTML="";accessories.innerHTML="";
 products.forEach(p=>{const card=document.createElement("div");card.className="product";const img=document.createElement("img");img.src=p.image;img.alt=p.name;img.loading="lazy";img.onerror=function(){this.onerror=null;this.src="https://placehold.co/600x400?text="+encodeURIComponent(p.name);};
 const name=document.createElement("h3");name.textContent=p.name;const price=document.createElement("p");price.className="price";price.textContent="₹"+p.price;
 const btn=document.createElement("button");btn.className="action";btn.textContent="Add to Cart 🛒";btn.onclick=()=>addToCart(p.id);card.append(img,name,price,btn);(p.category==="food"?food:accessories).appendChild(card);});
}
let cart=[];try{cart=JSON.parse(localStorage.getItem("petCart"))||[];}catch(e){cart=[];}
function saveCart(){localStorage.setItem("petCart",JSON.stringify(cart));displayCart();}
function addToCart(id){const p=products.find(x=>x.id===id),item=cart.find(x=>x.id===id);if(!p)return;if(item)item.quantity++;else cart.push({id,quantity:1});saveCart();alert(p.name+" added to cart!");}
function changeQuantity(id,amount){const item=cart.find(x=>x.id===id);if(!item)return;item.quantity+=amount;if(item.quantity<=0)cart=cart.filter(x=>x.id!==id);saveCart();}
function removeItem(id){cart=cart.filter(x=>x.id!==id);saveCart();}
function displayCart(){
 const area=document.getElementById("cartItems");area.innerHTML="";let total=0,count=0;
 if(!cart.length)area.textContent="Your cart is empty!";
 cart.forEach(item=>{const p=products.find(x=>x.id===item.id);if(!p)return;total+=p.price*item.quantity;count+=item.quantity;
 const row=document.createElement("div");row.className="cart-item";const info=document.createElement("div");info.className="cart-product";const img=document.createElement("img");img.src=p.image;img.alt=p.name;const details=document.createElement("span");details.textContent=p.name+" - ₹"+p.price;info.append(img,details);
 const controls=document.createElement("div");const minus=document.createElement("button");minus.textContent="−";minus.onclick=()=>changeQuantity(item.id,-1);const qty=document.createElement("span");qty.textContent=" "+item.quantity+" ";const plus=document.createElement("button");plus.textContent="+";plus.onclick=()=>changeQuantity(item.id,1);const remove=document.createElement("button");remove.textContent="Remove";remove.onclick=()=>removeItem(item.id);controls.append(minus,qty,plus,remove);row.append(info,controls);area.appendChild(row);});
 document.getElementById("total").textContent=total;document.getElementById("cartCount").textContent="Items: "+count;
}
function clearCart(){if(!cart.length){alert("Your cart is already empty!");return;}if(confirm("Do you want to clear your cart?")){cart=[];saveCart();}}
function checkout(){if(!cart.length){alert("Your cart is empty!");return;}let total=cart.reduce((sum,item)=>{const p=products.find(x=>x.id===item.id);return sum+(p?p.price*item.quantity:0);},0);if(confirm("Your total bill is ₹"+total+". Do you want to place your order?")){alert("Thank you for shopping with PetCare!\\nTotal: ₹"+total+"\\n\\nThis is a demo checkout. No real payment was made.");cart=[];saveCart();}}
document.getElementById("feedbackForm").addEventListener("submit",function(e){e.preventDefault();alert("Thank you for your feedback!");this.reset();});
displayProducts();displayCart();
</script>
</body>
</html>

# index.html  
  
<!DOCTYPE html>  
<html>  
<head>  
  <title>239 Market</title>  
  <style>  
    body { margin:0; font-family:Arial; background:#f3f3f3; }  
  
    header {  
      background:#131921;  
      color:white;  
      display:flex;  
      justify-content:space-between;  
      padding:15px;  
      align-items:center;  
    }  
  
    .logo { font-size:22px; font-weight:bold; }  
  
    .search input {  
      padding:8px;  
      width:300px;  
    }  
  
    .products {  
      display:grid;  
      grid-template-columns: repeat(auto-fill, minmax(200px,1fr));  
      gap:20px;  
      padding:20px;  
    }  
  
    .card {  
      background:white;  
      padding:15px;  
      border-radius:5px;  
      box-shadow:0 0 5px rgba(0,0,0,0.1);  
      text-align:center;  
    }  
  
    button {  
      background:#ff9900;  
      border:none;  
      padding:10px;  
      cursor:pointer;  
      width:100%;  
    }  
  
    .cart {  
      cursor:pointer;  
    }  
  </style>  
</head>  
  
<body>  
  
<header>  
  <div class="logo">239 Market</div>  
  
  <div class="search">  
    <input type="text" placeholder="Search products...">  
  </div>  
  
  <div class="cart" onclick="openCart()">  
    🛒 Cart (<span id="count">0</span>)  
  </div>  
</header>  
  
<section class="products" id="products"></section>  
  
<script>  
  let cart = [];  
  
  const products = [  
    {name:"Phone", price:200000},  
    {name:"Shoes", price:50000},  
    {name:"Watch", price:30000},  
    {name:"Bag", price:40000}  
  ];  
  
  const container = document.getElementById("products");  
  
  products.forEach(p => {  
    container.innerHTML += `  
      <div class="card">  
        <h3>${p.name}</h3>  
        <p>${p.price} RWF</p>  
        <button onclick="addToCart('${p.name}')">Add to Cart</button>  
      </div>  
    `;  
  });  
  
  function addToCart(name){  
    cart.push(name);  
    document.getElementById("count").innerText = cart.length;  
  }  
  
  function openCart(){  
    alert("Cart: " + cart.join(", "));  
  }  
</script>  
  
</body>  
</html>  

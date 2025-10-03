# JKS-MY-ALL.IN.ONE-APP
ALL NEEDS IN ONE APP
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>JKS Group Multi-Module Platform</title>
  <style>
    body {background: #20242b; color: #fff; font-family: 'Segoe UI', Arial, sans-serif; margin:0; padding:0;}
    header {background: #141b29; color: #00e1ff; font-size: 2.3rem; font-weight: 700; letter-spacing: 2px; padding: 20px 0; text-align: center; text-shadow: 0 0 22px #0fccfcbb;}
    nav {background: #141b29; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; border-bottom: 2px solid #00e1ff; padding: 10px 5px;}
    nav button {background: none; border: 2px solid #0fccfc; border-radius: 12px; color: #0fccfc; cursor: pointer; font-weight: 700; padding: 10px 16px; font-size: 1rem; min-width: 100px; transition:0.2s;}
    nav button:hover {background: #0fccfc; color: #202733;}
    main {max-width:1200px; margin:30px auto 60px; padding:0 10px;}
    /* Horizontal scroll containers */
    .dashboard, .service-list, .events-categories, #ecomCategoryList {
      display: flex;
      gap: 20px;
      overflow-x: auto;
      padding-bottom: 12px;
      -webkit-overflow-scrolling: touch;
      scrollbar-width: thin;
      scrollbar-color: #0fccfc #23273b;
    }
    .dashboard::-webkit-scrollbar, .service-list::-webkit-scrollbar, .events-categories::-webkit-scrollbar, #ecomCategoryList::-webkit-scrollbar {
      height: 10px;
    }
    .dashboard::-webkit-scrollbar-thumb, .service-list::-webkit-scrollbar-thumb, .events-categories::-webkit-scrollbar-thumb, #ecomCategoryList::-webkit-scrollbar-thumb {
      background-color: #0fccfc;
      border-radius: 10px;
    }
    .folder-card, .service-card, .category-card {
      background:#23273b; border:3px solid #ffe27f; border-radius:18px; padding: 30px 20px; font-size: 1.18em; font-weight:700; color:#ffe27f; cursor:pointer; text-align:center; box-shadow: 0 0 18px 5px #ffe27fab, 0 6px 29px #102733d8;
      flex: 0 0 200px;
      transition: transform 0.2s ease, background-color 0.2s ease, color 0.2s ease;
      white-space: normal;
      user-select: none;
    }
    .folder-card:hover, .service-card:hover, .category-card:hover {
      background:#ffe27f; color:#222a39; border-color:#0fccfc; box-shadow: 0 0 36px 11px #0fccfcbb, 0 6px 29px #23536fab; font-weight:900; transform: scale(1.06);
    }
    .section-title {font-size:1.6rem; font-weight:700; text-align:center; color:#ffe27f; margin-bottom:25px; text-shadow:0 0 17px #ffe27fac;}
    form.contact-form {max-width:420px; margin:20px auto 38px; padding:28px 18px; background:#172440; border-radius:14px; border:2px solid #00e1ff99; font-size:1.05em;}
    form.contact-form label {margin-bottom:7px; display:block; font-weight:700; color:#8ec7ff;}
    form.contact-form input, form.contact-form textarea, form.contact-form select {
      width:100%; padding:11px 14px; font-size:15px; margin-bottom:16px; border-radius:8px; border:1.4px solid #38abf7; background:#0f1f3a; color:#cde4ff; box-sizing:border-box;
    }
    form.contact-form input:focus, form.contact-form textarea:focus, form.contact-form select:focus { background:#1a4490; border-color:#00bfff; }
    form.contact-form button {width:100%; padding:15px 0; font-weight:900; font-size:1.12em; color:#192b3a; background:#00e1ff; border:none; border-radius:12px; cursor:pointer;}
    form.contact-form button:hover {background:#3de1ff;}
    .back-btn {display:block; margin:20px auto 16px; padding:15px 50px; font-weight:900; font-size:1.05em; border-radius:14px; background:#ffe27f; border:3px solid #ffe27f; color:#202733; cursor:pointer; width:max-content; box-shadow:0 0 28px 10px #ffe27f88;}
    .back-btn:hover {background:#00e1ff; color:#fff; border-color:#00e1ff; box-shadow:0 0 36px 11px #00e1ffcc;}
    #cartItemsCount {background:#ffe27f; color:#222a39; border-radius:50%; padding:0 10px; font-size:1.1em; font-weight:900; display:inline-block; margin-left:4px;}
    video#video {max-width:100%; border-radius:14px; border:2px solid #00e1ff8f; margin-top:18px;}
    #map {max-width:640px; height:420px; margin:20px auto 42px; border-radius:14px; border:3px solid #00e1ff94; box-shadow:0 0 27px 11px #00e1ff52;}
    img.media-thumb, video.media-thumb {max-width:150px; border-radius:12px; box-shadow:0 0 18px 5px #ffe27fab; cursor:pointer;}
    video.media-thumb {max-width:300px; box-shadow:0 0 18px 5px #0fccfcbb;}
    #mediaGallery {margin-top:20px; display:flex; flex-wrap:wrap; justify-content:center; gap:15px; border-top:2px solid #ffe27f; padding-top:15px;}
    @media(max-width:900px){
      main {padding: 0 12px;}
      .dashboard, .service-list, .events-categories, #ecomCategoryList {
        flex-wrap: wrap;
      }
      .folder-card, .service-card, .category-card {
        flex: 1 1 45%;
      }
    }
  </style>
</head>
<body>
<header>JKS Group of Business</header>
<nav>
  <button onclick="showPage('dashboard')">Dashboard</button>
  <button onclick="showPage('profile')">Profile</button>
  <button onclick="showPage('wallet')">Wallet</button>
  <button onclick="showPage('orders')">Orders</button>
  <button onclick="showPage('camera')">Camera</button>
  <button onclick="showPage('maps')">Google Maps</button>
</nav>
<main>
<section id="dashboard" class="dashboard"></section>

<section id="profile" style="display:none;">
  <h2 class="section-title">Profile</h2>
  <form class="contact-form" id="profileForm">
    <label>Name:</label>
    <input id="profileName" type="text" required/>
    <label>Email:</label>
    <input id="profileEmail" type="email"/>
    <label>Phone:</label>
    <input id="profilePhone" type="tel" maxlength="10" required/>
    <label>Address:</label>
    <textarea id="profileAddress" rows="3"></textarea>
    <button type="submit">Save</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="wallet" style="display:none;">
  <h2 class="section-title">Wallet</h2>
  <p>Balance: ₹<span id="walletBalance">10000</span></p>
  <form class="contact-form" onsubmit="addMoney(event)">
    <label>Add Money:</label>
    <input id="addMoneyInput" type="number" min="1" required/>
    <button type="submit">Add Funds</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="orders" style="display:none;">
  <h2 class="section-title">Orders</h2>
  <table style="width:100%;background:#1c2238;color:#fff;border-radius:8px;overflow:hidden;">
    <thead><tr><th style="padding:8px;">Order ID</th><th>Product / Service</th><th>Status</th></tr></thead>
    <tbody>
      <tr><td>001</td><td>Pizza</td><td style="color:#3eff9d;">Delivered</td></tr>
      <tr><td>002</td><td>Car Wash</td><td style="color:#ffe27f;">Pending</td></tr>
      <tr><td>003</td><td>Loan Enquiry</td><td style="color:#0bcfff;">In Progress</td></tr>
    </tbody>
  </table>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="serviceView" style="display:none;flex-direction:column;align-items:center;">
  <h2 class="section-title" id="serviceTitle"></h2>
  <div class="service-list" id="serviceList"></div>
  <form class="contact-form" id="contactForm" style="display:none;" onsubmit="event.preventDefault(); submitWhatsApp();">
    <label>Name:</label>
    <input id="userName" type="text" required/>
    <label>Mobile:</label>
    <input id="userPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required/>
    <label>Message:</label>
    <textarea id="userMessage" rows="4" required></textarea>
    <button type="submit">Send WhatsApp</button>
    <button type="button" class="back-btn" onclick="backToServiceList()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="events" style="display:none;flex-direction:column;align-items:center; max-width: 960px; margin: 0 auto;">
  <h2 class="section-title">Events & Catering</h2>
  <div class="events-categories" id="eventsCategories"></div>
  <div class="service-list" id="eventsServiceList" style="margin-top: 24px;"></div>
  <div id="mediaGallery"></div>
  <button onclick="showCart()" style="width:130px;margin: 10px auto 0; font-weight: 700; font-size: 1.1em; background:#0fccfc; border:none; border-radius:12px; padding:10px; color:#202733; box-shadow: 0 0 18px 6px #00e1ff99; cursor:pointer;">View Cart <span id='cartItemsCount'>0</span></button>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="ecommerce" style="display:none;flex-direction:column;align-items:center; max-width: 960px; margin: 0 auto;">
  <h2 class="section-title">My E-commerce</h2>
  <div id="ecomCategoryList" style="margin-bottom: 24px;"></div>
  <div class="service-list" id="ecomServiceList"></div>
  <form id="ecomOrderForm" class="contact-form" style="display:none;">
    <h3 id="ecomOrderTitle"></h3>
    <label>Name:</label>
    <input name="name" type="text" required/>
    <label>Mobile:</label>
    <input name="phone" pattern="[6-9][0-9]{9}" maxlength="10" type="tel" required/>
    <label>Order Details:</label>
    <textarea name="orderDetails" rows="3" required></textarea>
    <label>Delivery Address:</label>
    <textarea name="address" required></textarea>
    <button type="submit">Order WhatsApp</button>
    <button type="button" class="back-btn" onclick="backToEcomServices()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="recharge" style="display:none;flex-direction:column;align-items:center; max-width: 960px; margin: 0 auto;">
  <h2 class="section-title">Recharge & Pay Bills</h2>
  <div class="service-list" id="rechargeServiceList"></div>
  <form id="rechargeOrderForm" class="contact-form" style="display:none;">
    <h3 id="rechargeOrderTitle"></h3>
    <label>Name:</label>
    <input name="rname" type="text" required/>
    <label>Mobile:</label>
    <input name="rphone" pattern="[6-9][0-9]{9}" maxlength="10" type="tel" required/>
    <label>Order Details:</label>
    <textarea name="rdetails" rows="3" required></textarea>
    <label>Delivery Address (Optional):</label>
    <textarea name="raddress"></textarea>
    <button type="submit">Order WhatsApp</button>
    <button type="button" class="back-btn" onclick="backToRecharge()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="advertisement" style="display:none;flex-direction:column;align-items:center; max-width: 960px; margin: 0 auto;">
  <h2 class="section-title">Advertisement & Services</h2>
  <div class="service-list" id="advertisementServices"></div>
  <form class="contact-form" id="advertisementForm" style="display:none;" onsubmit="event.preventDefault(); submitAdvertisement();">
    <label>Name:</label>
    <input id="advName" type="text" required/>
    <label>Phone:</label>
    <input id="advPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required/>
    <label>Message:</label>
    <textarea id="advMessage" rows="4" required></textarea>
    <button type="submit">Send WhatsApp</button>
    <button type="button" class="back-btn" onclick="renderAdvertisement()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="camera" style="display:none;text-align:center;">
  <h2 class="section-title">Camera</h2>
  <video id="video" autoplay muted playsinline></video>
  <div style="margin:20px 0;">
    <button onclick="switchCamera()">Switch Camera</button>
    <button onclick="capturePhoto()">Capture Photo</button>
  </div>
  <canvas id="canvas" style="display:none;"></canvas>
  <div id="photoOutput"></div>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<section id="maps" style="display:none;text-align:center;">
  <h2 class="section-title">Google Maps</h2>
  <iframe id="map" width="100%" height="420" style="border:0; border-radius:14px;" loading="lazy"
          allowfullscreen referrerpolicy="no-referrer-when-downgrade"
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3806.272668041566!2d78.48261611487654!3d17.385044788065196!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bcb9736285f645f%3A0xf4dae048bfe79116!2sHyderabad!5e0!3m2!1sen!2sin!4v1633072783551!5m2!1sen!2sin"></iframe>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>

<div id="cartModal" style="display:none;position:fixed;top:10%;left:50%;transform:translateX(-50%);background:#202733;padding:24px 14px 14px 14px;z-index:9999;border-radius:14px;box-shadow:0 0 14px 6px #00e1ff99;width:350px;">
  <h3 style="color:#ffe27f;text-align:center;">Your Cart</h3>
  <ul id="cartList" style="margin-bottom:18px;padding-left:10px;"></ul>
  <button id="cartOrderBtn" style="width:100%;">Order via WhatsApp</button>
  <button onclick="closeCartModal()" style="background:#ff6464;color:#fff;width:100%;margin-top:7px;">Close</button>
</div>

<div id="cartDetailsModal" style="display:none;position:fixed;top:12%;left:50%;transform:translateX(-50%);background:#202733;padding:24px 14px 14px 14px;z-index:9999;border-radius:14px;box-shadow:0 0 16px 5px #00e1ff99;width:350px;">
  <h3 style="color:#ffe27f;text-align:center;">Your Details</h3>
  <form id="cartDetailsForm" class="contact-form" style="margin-top:0;">
    <label>Name:</label><input id="cartName" type="text" required/>
    <label>Mobile:</label><input id="cartPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required/>
    <label>Address:</label><textarea id="cartAddress" rows="3" required></textarea>
    <label>Message:</label><textarea id="cartMsg" rows="3" required></textarea>
    <button type="submit">Submit Order via WhatsApp</button>
    <button type="button" style="background:#ff6464;color:#fff;" onclick="closeCartDetailsModal()">Cancel</button>
  </form>
</div>
</main>
<script>
const folders = [
  {id:'ecommerce', label:'My E-commerce'},
  {id:'events', label:'Events & Catering'},
  {id:'courier', label:'Courier & Ride Booking'},
  {id:'job', label:'Job Consultancy & Services'},
  {id:'tours', label:'Tours & Travels'},
  {id:'realestate', label:'Real Estate & Construction'},
  {id:'investment', label:'Investment & Business'},
  {id:'loans', label:'Loans & Insurance'},
  {id:'home', label:'Home Services'},
  {id:'recharge', label:'Recharge & Pay Bills'},
  {id:'advertisement', label:'Advertisement & Services'}
];
const moduleServices = {
  courier:['Courier Booking','Ride Booking','Tracking','Support','Rental Vehicles'],
  job:['Job Search','Post Resume','Local Jobs','Non-Local Jobs','PG & Hostel','Services Marketplace'],
  tours:['Tour Bookings','Custom & Regular Tours','Stay Booking','Vehicle Booking','Train/Bus/Flight Tickets'],
  realestate:['Buy','Sell','Rent','Key Services','Construction','Industry'],
  investment:['Gold','Silver','Real Estate','Business Opportunity','Mutual Funds'],
  loans:['Loan Enquiry','Car Insurance','Bike Insurance','Housing Loans','Personal Loans','Health Insurance'],
  home:['CC Camera Installation','Computer Repair','Car Wash','Mobile Repair','Chef Services','Bouncers','Bike Mechanic','Car Mechanic','Electrician','Painter','Plumber','Driver']
};
const ecom = {
  Groceries:['Milk','Meat','Fruits','Vegetables','Flowers','Others'],
  Food:['Biriyani','Tiffins','Ice Cream','Pizza','Burgers','Rolls'],
  Pharmacy:['Medicines','Health Products','Supplements','Care Products']
};
const eventsCategories = {
  package: [
    {name:'Silver', amount:'50k - 160k'},
    {name:'Gold', amount:'150k - 300k'},
    {name:'Diamond', amount:'500k - 5M'},
    {name:'Platinum', amount:'500k - 800k'}
  ],
  customized: ['Decoration','Catering','Photography & Videography','Anchor & Actors','DJ & Singers','Guest House','Chocolate & Cake','Games & Entertainment','Jewellery','Invitation Cards','Vehicles','Return Gifts','Makeup Artist','Mehandi Artist','Clothing & Accessories'],
  premium: ['Decoration','Catering','Photography & Videography','Anchor & Actors','DJ & Singers','Guest House','Chocolate & Cake','Games & Entertainment','Jewellery','Invitation Cards','Vehicles','Return Gifts','Makeup Artist','Mehandi Artist','Clothing & Accessories']
};
const rechargeServices = ['Mobile Recharge','DTH Recharge','Electricity Bill','Water Bill','Gas Bill'];
const advertisementServices = [
  'Influencer Marketing',
  'Social Media Marketing',
  'Banner Ads - Complete Distribution',
  'Banner Ads - Poster Laying on Walls',
  'Banner Ads - Cycling Ads',
  'Banner Ads - Drone Ads',
  'Banner Ads - Vehicle Ads',
  'Video Making & Editing',
  'Poster Design',
  'Voice Over'
];
const servicesMedia = {
  customized: {
    'Decoration': [
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Decoration+1'},
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Decoration+2'},
      {type: 'video', src: 'https://sample-videos.com/video123/mp4/240/big_buck_bunny_240p_5mb.mp4'}
    ],
    'Catering': [
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Veg+Catering'},
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Nonveg+Catering'},
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Mixed+Catering'}
    ],
    'Photography & Videography': [
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Photography1'},
      {type: 'video', src: 'https://sample-videos.com/video123/mp4/240/big_buck_bunny_240p_1mb.mp4'}
    ]
  },
  premium: {
    'Decoration': [
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Premium+Decoration+1'},
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Premium+Decoration+2'}
    ],
    'Catering': [
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Premium+Catering+1'},
      {type: 'video', src: 'https://sample-videos.com/video123/mp4/240/big_buck_bunny_240p_5mb.mp4'}
    ],
    'Photography & Videography': [
      {type: 'image', src: 'https://via.placeholder.com/300x200?text=Premium+Photo1'},
      {type: 'video', src: 'https://sample-videos.com/video123/mp4/240/big_buck_bunny_240p_1mb.mp4'}
    ]
  }
};
let currentModule='', currentService='', currentEcomCategory='', currentRechargeService='', currentEventCategory='';
const whatsappNumber = '918977143043';

function clearInputs(ids){
  ids.forEach(id=>{
    const e=document.getElementById(id);
    if(e) e.value='';
  });
}
function capitalize(s){
  if(!s) return '';
  return s.charAt(0).toUpperCase()+s.slice(1);
}
function showPage(page){
  document.querySelectorAll('main > section').forEach(s=>s.style.display='none');
  clearMediaGallery();
  if(page === 'dashboard') renderDashboard();
  else if(page === 'events') openEvents();
  else if(page === 'ecommerce') openEcom();
  else if(page === 'recharge') openRecharge();
  else if(page === 'advertisement') renderAdvertisement();
  else if(page === 'camera') startCamera();
  else if(page === 'profile') fillProfile();
  else if(page === 'wallet') updateWallet();
  document.getElementById(page).style.display='block';
}
function renderDashboard(){
  const dash=document.getElementById('dashboard');
  dash.innerHTML='';
  folders.forEach(f=>{
    const div=document.createElement('div');
    div.className='folder-card';
    div.textContent = f.label;
    div.onclick = ()=>openModule(f.id);
    dash.appendChild(div);
  });
}
function openModule(mod){
  currentModule=mod; currentService='';
  if(mod==='events'){openEvents();return;}
  if(mod==='ecommerce'){openEcom();return;}
  if(mod==='recharge'){openRecharge();return;}
  if(mod==='advertisement'){renderAdvertisement();showPage('advertisement');return;}
  const servList=document.getElementById('serviceList');
  servList.innerHTML='';
  (moduleServices[mod]||[]).forEach(s=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=s;
    d.onclick=()=>openContactForm(s);
    servList.appendChild(d);
  });
  document.getElementById('serviceTitle').textContent=folders.find(f=>f.id===mod)?.label||'';
  showPage('serviceView');
}
function openContactForm(service){
  currentService=service;
  document.getElementById('serviceList').style.display='none';
  document.getElementById('contactForm').style.display='block';
  clearInputs(['userName','userPhone','userMessage']);
}
function backToServiceList(){
  document.getElementById('contactForm').style.display='none';
  document.getElementById('serviceList').style.display='flex';
}
function submitWhatsApp(){
  const name=document.getElementById('userName').value.trim();
  const phone=document.getElementById('userPhone').value.trim();
  const msg=document.getElementById('userMessage').value.trim();
  if(!name || !phone || !msg){alert('Please fill all fields');return;}
  const waMsg=`Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(currentService)}%0AMessage: ${encodeURIComponent(msg)}`;
  window.open(`https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${waMsg}`, '_blank');
}
let cartItems=JSON.parse(localStorage.getItem('jksCart')||'[]');
function saveCart(){localStorage.setItem('jksCart', JSON.stringify(cartItems)); updateCartCount();}
function updateCartCount(){document.getElementById('cartItemsCount').textContent=cartItems.length;}
function addToCart(item){
  if(cartItems.find(ci => ci.name === item.name && ci.category === item.category)){
    alert(`${item.name} is already in cart!`);
    return;
  }
  cartItems.push(item); saveCart(); alert(`${item.name} Added to Cart!`);
}
function showCart(){
  updateCartCount();
  const cartModal=document.getElementById('cartModal');
  const cartList=document.getElementById('cartList');
  cartList.innerHTML='';
  if(cartItems.length===0){
    cartList.innerHTML='<li style="color:#ffe27f;">Cart is empty!</li>';
    document.getElementById('cartOrderBtn').disabled=true;
  }else{
    cartItems.forEach((item,i)=>{
      const li=document.createElement('li');
      li.style.marginBottom='8px'; li.style.color='#ffe27f';
      li.textContent=`${item.category.toUpperCase()} - ${item.name}${item.budget?(' | Budget: '+item.budget):''}${item.capacity?(' | Capacity: '+item.capacity):''}`;
      const remBtn=document.createElement('button');
      remBtn.textContent='Remove'; remBtn.style.marginLeft='8px';
      remBtn.onclick=()=>{cartItems.splice(i,1);saveCart();showCart();}
      li.appendChild(remBtn);
      cartList.appendChild(li);
    });
    document.getElementById('cartOrderBtn').disabled=false;
  }
  cartModal.style.display='block';
}
function closeCartModal(){document.getElementById('cartModal').style.display='none';}
function closeCartDetailsModal(){document.getElementById('cartDetailsModal').style.display='none';}
document.getElementById('cartOrderBtn').onclick=function(){
  closeCartModal();
  document.getElementById('cartDetailsModal').style.display='block';
};
document.getElementById('cartDetailsForm').onsubmit=function(e){
  e.preventDefault();
  const name=document.getElementById('cartName').value.trim();
  const phone=document.getElementById('cartPhone').value.trim();
  const address=document.getElementById('cartAddress').value.trim();
  const msg=document.getElementById('cartMsg').value.trim();
  if(!name||!phone||!address||!msg){alert('Please fill all fields');return;}
  if(cartItems.length===0){alert('Cart is empty!');closeCartDetailsModal();return;}
  let waMsg=`Events & Catering Order%0AName: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AAddress: ${encodeURIComponent(address)}%0AMessage: ${encodeURIComponent(msg)}%0A%0AOrder Details:`;
  cartItems.forEach((item,i)=>{
    waMsg+=`%0A${i+1}. ${item.category.toUpperCase()} - ${encodeURIComponent(item.name)}`;
    if(item.budget) waMsg+=` | Budget: ${encodeURIComponent(item.budget)}`;
    if(item.capacity) waMsg+=` | Capacity: ${encodeURIComponent(item.capacity)}`;
  });
  window.open(`https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${waMsg}`,'_blank');
  cartItems=[]; saveCart(); closeCartDetailsModal();
};
function openEvents(){
  currentEventCategory='';
  document.getElementById('dashboard').style.display='none';
  document.getElementById('events').style.display='flex';
  const cats=document.getElementById('eventsCategories');
  cats.innerHTML='';
  ['package','customized','premium'].forEach(cat=>{
    const d=document.createElement('div');
    d.className='category-card'; d.textContent=capitalize(cat);
    d.onclick=()=>openEventsCategory(cat);
    cats.appendChild(d);
  });
  document.getElementById('eventsServiceList').innerHTML='';
  clearMediaGallery();
}
function openEventsCategory(category){
  currentEventCategory=category;
  const svcList=document.getElementById('eventsServiceList');
  svcList.innerHTML='';
  svcList.style.display='flex';
  svcList.style.gap='20px';
  if(category==='package'){
    eventsCategories.package.forEach(pkg=>{
      const d=document.createElement('div');
      d.className='service-card';
      d.textContent=`${pkg.name} (${pkg.amount})`;
      const btn=document.createElement('button');
      btn.textContent='Add to Cart'; btn.style.marginTop='1rem';
      btn.onclick=()=>addToCart({category:'package',name:pkg.name,budget:pkg.amount});
      d.appendChild(btn); svcList.appendChild(d);
    });
  } else {
    eventsCategories[category].forEach(svc=>{
      const d=document.createElement('div');
      d.className='service-card'; d.textContent=svc;
      if(category==='customized'){
        const budgetLabel=document.createElement('label');budgetLabel.textContent='Budget: ';
        const budgetSelect=document.createElement('select');
        ['Select Budget','10k to 50k','50k to 1L','1L to 5L','5L to 10L','Above 10L'].forEach(b=>{
          const opt=document.createElement('option');opt.text=b;budgetSelect.appendChild(opt);
        });budgetLabel.appendChild(budgetSelect);
        const capacityLabel=document.createElement('label');capacityLabel.textContent='Capacity: ';
        const capacitySelect=document.createElement('select');
        ['Select Capacity','5-30 people','30-60 people','60-90 people','90-130 people','Above 130 people'].forEach(c=>{
          const opt=document.createElement('option');opt.text=c;capacitySelect.appendChild(opt);
        });capacityLabel.appendChild(capacitySelect);
        d.appendChild(document.createElement('br')); d.appendChild(budgetLabel); d.appendChild(capacityLabel);
        const btn=document.createElement('button');
        btn.textContent='Add to Cart'; btn.style.marginTop='1rem';
        btn.onclick=()=>{
          const budget=budgetSelect.value, capacity=capacitySelect.value;
          if(budget==='Select Budget'||capacity==='Select Capacity'){alert('Select budget and capacity'); return;}
          addToCart({category:'customized',name:svc,budget,capacity});
        };
        d.appendChild(btn);
        const mediaBtn=document.createElement('button');
        mediaBtn.textContent='View Samples'; mediaBtn.style.margin='10px 0 0 0';
        mediaBtn.onclick=()=>openServiceMedia('customized', svc);
        d.appendChild(mediaBtn);
      } else if(category==='premium'){
        const btn=document.createElement('button');
        btn.textContent='Add to Cart'; btn.style.marginTop='1rem';
        btn.onclick=()=>addToCart({category:'premium',name:svc});
        d.appendChild(btn);
        const mediaBtn=document.createElement('button');
        mediaBtn.textContent='View Samples'; mediaBtn.style.margin='10px 0 0 0';
        mediaBtn.onclick=()=>openServiceMedia('premium', svc);
        d.appendChild(mediaBtn);
      }
      svcList.appendChild(d);
    });
  }
  clearMediaGallery();
}
function clearMediaGallery(){
  const gallery=document.getElementById('mediaGallery');
  if(gallery) gallery.innerHTML='';
}
function openServiceMedia(category, service){
  clearMediaGallery();
  const gallery=document.getElementById('mediaGallery');
  const mediaItems=(servicesMedia[category] && servicesMedia[category][service]) || [];
  if(mediaItems.length===0){
    gallery.textContent='No media samples available for this service.';
    gallery.style.color='#ffe27f';
    return;
  }
  mediaItems.forEach(item=>{
    if(item.type==='image'){
      const img=document.createElement('img');
      img.src=item.src;
      img.className='media-thumb';
      gallery.appendChild(img);
    } else if(item.type==='video'){
      const vid=document.createElement('video');
      vid.src=item.src;
      vid.controls=true;
      vid.className='media-thumb';
      gallery.appendChild(vid);
    }
  });
}
// Profile
function saveProfile(){
  const name=document.getElementById('profileName').value.trim();
  const email=document.getElementById('profileEmail').value.trim();
  const phone=document.getElementById('profilePhone').value.trim();
  const address=document.getElementById('profileAddress').value.trim();
  if(!name || !phone){ alert('Name and phone are required!'); return; }
  localStorage.setItem('profileName', name);
  localStorage.setItem('profileEmail', email);
  localStorage.setItem('profilePhone', phone);
  localStorage.setItem('profileAddress', address);
  alert('Profile saved!');
}
function fillProfile(){
  document.getElementById('profileName').value=localStorage.getItem('profileName')||'';
  document.getElementById('profileEmail').value=localStorage.getItem('profileEmail')||'';
  document.getElementById('profilePhone').value=localStorage.getItem('profilePhone')||'';
  document.getElementById('profileAddress').value=localStorage.getItem('profileAddress')||'';
}
document.getElementById('profileForm').onsubmit=function(e){ e.preventDefault(); saveProfile(); };
// Wallet
function addMoney(event){
  event.preventDefault();
  let amount=parseFloat(document.getElementById('addMoneyInput').value);
  if(isNaN(amount) || amount <= 0){
    alert('Enter valid amount');
    return;
  }
  let wallet=localStorage.getItem('walletBalance');
  wallet=wallet?parseFloat(wallet):10000;
  wallet+=amount;
  localStorage.setItem('walletBalance', wallet);
  updateWallet(); alert('Added ₹'+amount);
  document.getElementById('addMoneyInput').value='';
}
function updateWallet(){
  let wallet=localStorage.getItem('walletBalance');
  wallet=wallet?parseFloat(wallet):10000;
  document.getElementById('walletBalance').textContent=wallet.toFixed(2);
}
// Ecommerce
function openEcom(){
  currentEcomCategory='';
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('events').style.display='none';
  document.getElementById('recharge').style.display='none';
  document.getElementById('ecommerce').style.display='flex';
  const ecomCatList=document.getElementById('ecomCategoryList');
  ecomCatList.innerHTML='';
  Object.keys(ecom).forEach(cat=>{
    const div=document.createElement('div');
    div.className='folder-card';
    div.textContent=cat;
    div.onclick=()=>openEcomCategory(cat);
    ecomCatList.appendChild(div);
  });
  document.getElementById('ecomServiceList').innerHTML='';
}
function openEcomCategory(cat){
  currentEcomCategory=cat;
  const svcList=document.getElementById('ecomServiceList');
  svcList.innerHTML='';
  (ecom[cat]||[]).forEach(svc=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=svc;
    d.onclick=()=>openEcomOrderForm(cat, svc);
    svcList.appendChild(d);
  });
  document.getElementById('ecomOrderForm').style.display='none';
}
function openEcomOrderForm(cat, svc){
  document.getElementById('ecomOrderForm').style.display='block';
  document.getElementById('ecomOrderTitle').textContent=`Order ${svc} in ${cat}`;
  document.getElementById('ecomOrderForm').onsubmit=function(e){
    e.preventDefault();
    const n=document.querySelector('#ecomOrderForm input[name="name"]').value.trim();
    const p=document.querySelector('#ecomOrderForm input[name="phone"]').value.trim();
    const d=document.querySelector('#ecomOrderForm textarea[name="orderDetails"]').value.trim();
    const a=document.querySelector('#ecomOrderForm textarea[name="address"]').value.trim();
    if(!n || !p || !d || !a){alert('Fill all order fields');return;}
    const msg=`Order: ${svc}\nName: ${n}\nPhone: ${p}\nDetails: ${d}\nAddress: ${a}`;
    window.open(`https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${encodeURIComponent(msg)}`,'_blank');
  }
}
function backToEcomServices(){
  document.getElementById('ecomOrderForm').style.display='none';
}
// Recharge
function openRecharge(){
  currentRechargeService='';
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('events').style.display='none';
  document.getElementById('ecommerce').style.display='none';
  document.getElementById('recharge').style.display='flex';
  const rechargeList=document.getElementById('rechargeServiceList');
  rechargeList.innerHTML='';
  rechargeServices.forEach(svc=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=svc;
    d.onclick=()=>openRechargeOrderForm(svc);
    rechargeList.appendChild(d);
  });
  document.getElementById('rechargeOrderForm').style.display='none';
}
function openRechargeOrderForm(svc){
  currentRechargeService=svc;
  document.getElementById('rechargeServiceList').style.display='none';
  const form=document.getElementById('rechargeOrderForm');
  form.style.display='block';
  document.getElementById('rechargeOrderTitle').textContent='Pay ' + svc;
  const inputs=form.querySelectorAll('input,textarea');
  inputs.forEach(i=>i.value='');
  form.onsubmit=function(e){
    e.preventDefault();
    const n=document.querySelector('input[name="rname"]').value.trim();
    const p=document.querySelector('input[name="rphone"]').value.trim();
    const d=document.querySelector('textarea[name="rdetails"]').value.trim();
    const a=document.querySelector('textarea[name="raddress"]').value.trim();
    if(!n || !p || !d){alert('Fill all required fields');return;}
    const msg=`Recharge Payment: ${svc}\nName: ${n}\nPhone: ${p}\nDetails: ${d}\nAddress: ${a}`;
    window.open(`https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${encodeURIComponent(msg)}`,'_blank');
  }
}
function backToRecharge(){
  document.getElementById('rechargeOrderForm').style.display='none';
  document.getElementById('rechargeServiceList').style.display='flex';
}
// Advertisement
function renderAdvertisement(){
  const container=document.getElementById('advertisementServices');
  container.innerHTML='';
  advertisementServices.forEach(svc=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=svc;
    d.onclick=()=>openAdvertisementForm(svc);
    container.appendChild(d);
  });
  document.getElementById('advertisementForm').style.display='none';
}
let currentAdvService='';
function openAdvertisementForm(service){
  currentAdvService=service;
  document.getElementById('advertisementForm').style.display='block';
}
function submitAdvertisement(){
  const name=document.getElementById('advName').value.trim();
  const phone=document.getElementById('advPhone').value.trim();
  const message=document.getElementById('advMessage').value.trim();
  if(!name || !phone || !message){
    alert('Please fill all fields');
    return;
  }
  const msg=`Name: ${name}\nPhone: ${phone}\nService: ${currentAdvService}\nMessage: ${message}`;
  window.open(`https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${encodeURIComponent(msg)}`,'_blank');
  document.getElementById('advertisementForm').reset();
  document.getElementById('advertisementForm').style.display='none';
}
// Camera
let cameraStream=null; let frontCamera=true;
function startCamera(){
  if(cameraStream) cameraStream.getTracks().forEach(t=>t.stop());
  const video=document.getElementById('video');
  navigator.mediaDevices.getUserMedia({video:{facingMode:frontCamera?'user':'environment'}})
  .then(s=>{
    cameraStream=s;
    video.srcObject=s;
    video.play();
  }).catch(()=>alert('Camera not available'));
}
function switchCamera(){frontCamera=!frontCamera;startCamera();}
function capturePhoto(){
  const video=document.getElementById('video');
  const canvas=document.getElementById('canvas');
  canvas.width=video.videoWidth;
  canvas.height=video.videoHeight;
  canvas.getContext('2d').drawImage(video,0,0);
  const dataUrl=canvas.toDataURL();
  document.getElementById('photoOutput').innerHTML=`<img src="${dataUrl}" style="max-width:250px;border-radius:12px;"/>`;
}
// Initialization
document.addEventListener('DOMContentLoaded', ()=>{
  showPage('dashboard');
  fillProfile();
  updateWallet();
  updateCartCount();
});
</script>
</body>
</html>

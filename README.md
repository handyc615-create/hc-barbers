<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HC Barbers</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background:#deb887; /* woody brown */
      margin:0; padding:0; color:#333;
      transition: background 0.5s, color 0.5s;
    }
    h1,h2,h3,h4,h5,h6 { margin-bottom:10px; }
    p,li { margin-bottom:8px; }
    ul { margin-left:20px; }
    a { text-decoration:none; }
    a:hover { text-decoration:underline; }

    /* BUTTONS */
    .btn { background-color:#444; color:white; padding:10px 20px; border-radius:8px; font-weight:bold; cursor:pointer; display:inline-block; margin-top:10px; border:none; }
    .btn:hover { background:white; color:#444; border:1px solid #444; }

    /* HEADER NAVIGATION */
    header { background:#444; padding:10px; position:sticky; top:0; z-index:999; display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; }
    .logo { color:white; font-size:1.5em; font-weight:bold; }
    nav { display:flex; gap:10px; }
    .nav-btn { background:#444; padding:8px 15px; border-radius:5px; border:none; color:white; cursor:pointer; font-weight:bold; }
    .nav-btn:hover, .nav-btn.active { background:white; color:#444; border:1px solid #444; }

    /* Dropdown menu */
    .dropdown { position:relative; display:inline-block; }
    .dropdown-content { display:none; position:absolute; background:#f4f4f4; min-width:120px; box-shadow:0 2px 10px rgba(0,0,0,0.2); border-radius:5px; z-index:1; }
    .dropdown-content button { width:100%; text-align:left; padding:8px; border:none; background:none; cursor:pointer; }
    .dropdown-content button:hover { background:#ddd; color:#444; }
    .dropdown:hover .dropdown-content { display:block; }

    /* SECTIONS */
    section { background:#fff; border-radius:10px; padding:25px; margin:20px auto; max-width:1000px; box-shadow:0 2px 10px rgba(0,0,0,0.1); }
    .box { border:1px solid #ccc; padding:20px; border-radius:10px; margin-bottom:20px; background:#444; color:white; }
    .flex { display:flex; flex-wrap:wrap; gap:20px; }
    .card { flex:1 1 250px; background:#555; padding:15px; border-radius:10px; color:white; }

    /* HEADER BANNER */
    .banner { width:100%; height:250px; background-image: url('https://ih1.redbubble.net/image.1504768575.2001/flat,750x,075,f-pad,750x1000,f8f8f8.jpg'); background-size: cover; background-position:center; border-radius:10px; margin-bottom:20px; }

    /* FORM */
    form input, form select, form textarea, form button { width:100%; padding:10px; margin-bottom:10px; border-radius:6px; border:1px solid #ccc; }
    form button { background:#444; color:white; border:none; font-weight:bold; cursor:pointer; }
    form button:hover { background:#666; }

    /* AI CHAT BOX */
    #chat-container { position:fixed; bottom:20px; right:20px; width:280px; background:#fff; border-radius:10px; box-shadow:0 2px 12px rgba(0,0,0,0.2); font-size:0.9em; overflow:hidden; }
    #chat-header { background:#444; color:white; padding:10px; text-align:center; cursor:pointer; }
    #chat-body { display:none; max-height:300px; overflow-y:auto; padding:10px; }
    #chat-messages { margin-bottom:10px; }
    .message { margin-bottom:10px; }
    .bot { background:#f1f1f1; padding:5px 10px; border-radius:5px; color:black; }
    .user { background:#444; color:white; padding:5px 10px; border-radius:5px; text-align:right; }

    /* Star Rating */
    .star-rating { display:flex; flex-direction:row-reverse; font-size:1.5em; justify-content:flex-end; margin-bottom:10px; }
    .star-rating input { display:none; }
    .star-rating label { color:#ccc; cursor:pointer; }
    .star-rating input:checked ~ label,
    .star-rating label:hover,
    .star-rating label:hover ~ label { color:gold; }

    /* DARK MODE */
    body.dark { background:#000; color:white; }
    body.dark section.box { background:#222; color:white; }
    body.dark .card { background:#333; color:white; }
  </style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="logo">HC Barbers</div>
  <nav class="desktop-nav">
    <button class="nav-btn" onclick="scrollToSection('home')">Home</button>
    <button class="nav-btn" onclick="scrollToSection('barbers')">Barbers</button>
    <button class="nav-btn" onclick="scrollToSection('review')">Reviews</button>
    <button class="nav-btn" onclick="scrollToSection('locate')">Locate Us</button>
  </nav>
  <div class="dropdown">
    <button class="nav-btn">Menu ▾</button>
    <div class="dropdown-content">
      <button onclick="scrollToSection('home')">Home</button>
      <button onclick="scrollToSection('barbers')">Barbers</button>
      <button onclick="scrollToSection('review')">Reviews</button>
      <button onclick="scrollToSection('locate')">Locate Us</button>
    </div>
  </div>
  <button class="btn" onclick="toggleDarkMode()">Dark Mode</button>
</header>

<!-- BANNER -->
<div class="banner"></div>

<!-- HOME -->
<section class="box" id="home">
  <h1>Welcome to HC Barbers</h1>
  <p>Your local barber shop for clean cuts, great vibes, and professional service.</p>
</section>

<!-- BARBERS -->
<section class="box" id="barbers">
  <h2>Meet Our Barbers</h2>
  <div class="flex">
    <div class="card">
      <img src="https://randomuser.me/api/portraits/men/10.jpg" alt="Barber 1" style="width:100%; border-radius:10px;">
      <h3>Barber 1</h3>
      <p>Availability: Mon-Fri 10am-6pm</p>
      <a href="#" class="btn">Book Appointment</a>
    </div>
    <div class="card">
      <img src="https://randomuser.me/api/portraits/men/20.jpg" alt="Barber 2" style="width:100%; border-radius:10px;">
      <h3>Barber 2</h3>
      <p>Availability: Tue-Sat 11am-7pm</p>
      <a href="#" class="btn">Book Appointment</a>
    </div>
    <div class="card">
      <img src="https://randomuser.me/api/portraits/women/30.jpg" alt="Barber 3" style="width:100%; border-radius:10px;">
      <h3>Barber 3</h3>
      <p>Availability: Mon-Thu 9am-5pm</p>
      <a href="#" class="btn">Book Appointment</a>
    </div>
  </div>
</section>

<!-- REVIEWS -->
<section class="box" id="review">
  <h2>Reviews</h2>
  <p>Click to leave a review:</p>
  <a href="https://forms.gle/yourformlinkhere" class="btn" target="_blank">Leave a Review →</a>
</section>

<!-- LOCATE US -->
<section class="box" id="locate">
  <h2>Locate Us</h2>
  <img src="https://martech.org/wp-content/uploads/2016/10/local-location-targeting-geotargeting-pin-ss-1920.jpg"
       alt="HC Barbers Location"
       style="width:50%; max-width:400px; border-radius:10px; display:block; margin-left:auto; margin-right:auto;">
  <p style="text-align:center; margin-top:10px;">123 Main St, Queens, NY 11101</p>
</section>

<!-- AI CHAT BOX -->
<div id="chat-container">
  <div id="chat-header">😊 Click to Chat</div>
  <div id="chat-body">
    <div id="chat-messages"></div>
    <div id="chat-input">
      <input type="text" id="user-input" placeholder="Ask about bookings or services...">
      <button id="send-btn">Send</button>
    </div>
  </div>
</div>

<script>
  // Scroll
  function scrollToSection(id){
    document.getElementById(id).scrollIntoView({behavior:'smooth'});
  }

  // Dark Mode
  function toggleDarkMode(){
    document.body.classList.toggle('dark');
  }

  // AI Chat
  const chatHeader = document.getElementById('chat-header');
  const chatBody = document.getElementById('chat-body');
  chatHeader.addEventListener('click', () => {
    chatBody.style.display = chatBody.style.display==='block'?'none':'block';
  });

  const chatMessages = document.getElementById('chat-messages');
  const userInput = document.getElementById('user-input');
  const sendBtn = document.getElementById('send-btn');
  const botResponses = {
    'hello':'😊 Hi! Need a booking or info?',
    'hours':'😊 Our barbers are available Mon-Sun 9am-8pm depending on the barber.',
    'services':'😊 We offer haircuts, trims, shaves, and styling.',
    'booking':'😊 Click any barber\'s button to book an appointment.'
  };

  function addMessage(text,sender){
    const msg=document.createElement('div');
    msg.className='message '+sender;
    msg.innerText=text;
    chatMessages.appendChild(msg);
    chatMessages.scrollTop=chatMessages.scrollHeight;
  }

  sendBtn.addEventListener('click',()=>{
    const text=userInput.value.toLowerCase();
    if(!text) return;
    addMessage('🤔 '+text,'user');
    let reply='😢 Sorry, I do not understand. Try asking "hello", "hours", "services", or "booking".';
    for(const key in botResponses){ if(text.includes(key)) reply=botResponses[key]; }
    setTimeout(()=>addMessage(reply,'bot'),500);
    userInput.value='';
  });
</script>

<footer class="box">
  <p>© 2026 HC Barbers | Built by Handy Celestin</p>
</footer>

</body>
</html

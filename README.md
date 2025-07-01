<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Web Dev Roadmap | Student Portal</title>
  <style>
    /* Preloader Styles */
    #preloader {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      transition: opacity 0.6s ease;
    }

    #preloader img {
      width: 120px;
      animation: spin 2s linear infinite;
    }

    @keyframes spin {
      0% { transform: rotate(0); }
      100% { transform: rotate(360deg); }
    }

    body {
      font-family: 'Segoe UI', Tahoma, sans-serif;
      margin: 0;
      padding: 0;
      background: #f7f9fb;
      overflow-x: hidden;
    }

    header {
      background-color: #4a90e2;
      color: white;
      padding: 20px;
      text-align: center;
      animation: fadeDown 1s ease;
    }

    .container {
      max-width: 900px;
      margin: auto;
      padding: 20px;
      animation: fadeUp 1s ease;
    }

    .section, .form-section {
      background: white;
      margin-bottom: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      padding: 15px;
      opacity: 0;
      transform: translateY(20px);
      animation: slideIn 0.6s ease forwards;
      animation-delay: 0.3s;
    }

    .section h2 {
      margin: 0;
      cursor: pointer;
      padding-bottom: 10px;
      border-bottom: 1px solid #ccc;
    }

    .content {
      display: none;
      margin-top: 10px;
    }

    .active .content {
      display: block;
    }

    label, input, textarea, select {
      display: block;
      width: 100%;
      margin-top: 10px;
      padding: 8px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      margin-top: 15px;
      padding: 10px 20px;
      background: #4a90e2;
      border: none;
      color: white;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    button:hover {
      background: #3b78c2;
    }

    .login-box {
      background: white;
      padding: 20px;
      max-width: 400px;
      margin: 30px auto;
      box-shadow: 0 2px 6px rgba(0,0,0,0.2);
      border-radius: 10px;
      animation: fadeUp 1s ease;
    }

    a {
      color: #4a90e2;
      text-decoration: none;
    }

    a:hover {
      text-decoration: underline;
    }

    /* Animations */
    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeDown {
      from {
        opacity: 0;
        transform: translateY(-30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes slideIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  </style>
</head>
<body>

<!-- Splash Screen -->
<div id="preloader">
  <img src="logo.jpg" alt="Logo" />
</div>

<header>
  <h1>Web Development Training</h1>
  <p>Student Portal | Learn and Grow</p>
</header>

<!-- Student Login -->
<div class="login-box" id="loginBox">
  <h2>Student Login</h2>
  <label for="studentEmail">Email</label>
  <input type="email" id="studentEmail" placeholder="you@example.com" required />
  <label for="studentPassword">Password</label>
  <input type="password" id="studentPassword" placeholder="Enter password" required />
  <button onclick="login()">Login</button>
</div>

<!-- Main Content -->
<div class="container" id="roadmapContent" style="display:none;">

  <!-- Course Details -->
  <div class="section active">
    <h2>📘 Web Development Course Details</h2>
    <div class="content">
      <ul>
        <li><b>Duration:</b> 3 Months</li>
        <li><b>Modules:</b> HTML, CSS, JavaScript, React, Node.js</li>
        <li><b>Projects:</b> Portfolio, To-Do App, Blog App</li>
        <li><b>Support:</b> Live doubt sessions + PDF notes</li>
      </ul>
    </div>
  </div>

  <!-- Roadmap Sections -->
  <div class="section">
    <h2 onclick="toggleSection(this)">1. HTML & CSS Basics</h2>
    <div class="content">
      <ul>
        <li>HTML5, Forms, Semantic Elements</li>
        <li>CSS3, Flexbox, Grid</li>
        <li>Responsive Design (Media Queries)</li>
        <li>📖 <a href="https://www.tpointtech.com/html-tutorial" target="_blank">Reference</a></li>
      </ul>
    </div>
  </div>

  <div class="section">
    <h2 onclick="toggleSection(this)">2. JavaScript Fundamentals</h2>
    <div class="content">
      <ul>
        <li>Variables, Loops, Functions, DOM</li>
        <li>Events, Arrays, Objects</li>
        <li>ES6 (let, const, arrow functions)</li>
      </ul>
    </div>
  </div>

  <div class="section">
    <h2 onclick="toggleSection(this)">3. Frontend Frameworks</h2>
    <div class="content">
      <ul>
        <li>React.js (Components, Props, State)</li>
        <li>React Router Basics</li>
      </ul>
    </div>
  </div>

  <div class="section">
    <h2 onclick="toggleSection(this)">4. Backend & Databases</h2>
    <div class="content">
      <ul>
        <li>Node.js & Express.js</li>
        <li>REST APIs</li>
        <li>MongoDB / MySQL Basics</li>
      </ul>
    </div>
  </div>

  <!-- Tuition Interest Form -->
  <div class="form-section">
    <h2>📥 Interested in Online Tuition?</h2>
    <form onsubmit="submitForm(event)">
      <label for="name">Full Name</label>
      <input type="text" id="name" placeholder="Your Name" required />

      <label for="email">Email Address</label>
      <input type="email" id="email" placeholder="you@example.com" required />

      <label for="course">Course Interested In</label>
      <select id="course" required>
        <option value="">--Select--</option>
        <option>Frontend Development</option>
        <option>Full Stack Web Development</option>
        <option>JavaScript Mastery</option>
      </select>

      <label for="message">Message / Questions</label>
      <textarea id="message" rows="4" placeholder="Write here..."></textarea>

      <button type="submit">Submit</button>
    </form>
  </div>
</div>

<script>
  // Splash screen hide
  window.addEventListener('load', () => {
    const preloader = document.getElementById("preloader");
    setTimeout(() => {
      preloader.style.opacity = '0';
      preloader.style.pointerEvents = 'none';
      setTimeout(() => preloader.remove(), 500);
    }, 1500); // Delay
  });

  function toggleSection(header) {
    const section = header.parentElement;
    section.classList.toggle("active");
  }

  function login() {
    const email = document.getElementById("studentEmail").value;
    const password = document.getElementById("studentPassword").value;

    if (email && password) {
      document.getElementById("loginBox").style.display = "none";
      document.getElementById("roadmapContent").style.display = "block";
    } else {
      alert("Please enter valid credentials");
    }
  }

  function submitForm(event) {
    event.preventDefault();
    const name = document.getElementById("name").value;
    const email = document.getElementById("email").value;
    const course = document.getElementById("course").value;
    const msg = document.getElementById("message").value;

    alert(`Thank you, ${name}! We'll contact you soon about "${course}".`);
    event.target.reset();
  }
</script>

</body>
</html>

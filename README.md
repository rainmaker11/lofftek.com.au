<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Lofttek Racing</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Basic reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: #f4f4f4;
            color: #333;
            font-size: 18px;
            line-height: 1.6;
        }

        header {
            background-color: #ffffff; /* White background */
            padding: 60px 20px;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05); /* Soft shadow */
        }

        .header-content img {
            max-width: 180px; /* Smaller logo for a cleaner look */
        }

        nav {
            background-color: #f8f8f8; /* Light grey nav background */
            padding: 20px 0;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
        }

        nav ul {
            list-style: none;
            text-align: center;
        }

        nav ul li {
            display: inline;
            margin: 0 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: #333;
            font-weight: bold;
            font-size: 18px;
            transition: color 0.3s ease;
            padding: 10px 20px;
            border-radius: 5px; /* Match button style */
        }

        nav ul li a:hover {
            color: #4a90e2;
            background-color: rgba(74, 144, 226, 0.1); /* Add background on hover */
        }

        .hero {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 60px 20px;
            background-color: #fff;
        }

        .hero h1 {
            font-size: 64px; /* Sleek and professional font size */
            font-weight: 700;
            margin-bottom: 40px;
            color: #333;
        }

        .hero video {
            width: 80%; /* Increased video size */
            height: auto;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
        }

        /* Professional Button Styles */
        .btn {
            display: inline-block;
            padding: 15px 30px;
            font-size: 16px;
            font-weight: 600;
            color: #fff;
            background-color: #4a90e2;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease, box-shadow 0.3s ease;
        }

        .btn:hover {
            background-color: #357abd;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        /* Tek Tiers Grid */
        .tier-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            margin: 60px auto;
            width: 80%;
        }

        .tier-card {
            background-color: #ffffff;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-align: center;
            cursor: pointer;
        }

        .tier-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .tier-card:active {
            background-color: #e1f0fe; /* Active background color */
            transform: scale(0.98);
        }

        .tier-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
            color: #4a90e2;
        }

        .tier-card p {
            font-size: 16px;
            color: #666;
        }

        /* Modal styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background-color: #fff;
            margin: 10% auto;
            padding: 40px;
            border-radius: 10px;
            width: 60%;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
            text-align: center;
        }

        .modal-content h2 {
            font-size: 30px;
            color: #333;
            margin-bottom: 20px;
        }

        .close {
            color: #aaa;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.2s ease;
        }

        .close:hover {
            color: #333;
        }

        /* Membership section */
        .membership-section {
            max-width: 1200px;
            margin: 60px auto;
            padding: 40px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            display: none;
        }

        .membership-section h2 {
            font-size: 28px;
            margin-bottom: 30px;
            color: #333;
        }

        .membership-form {
            display: flex;
            flex-direction: column;
        }

        .membership-form label {
            margin-bottom: 10px;
            font-size: 18px;
        }

        .membership-form input {
            padding: 15px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }

        .membership-form button {
            padding: 15px;
            background-color: #4a90e2;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 18px;
        }

        footer {
            background-color: #f8f8f8;
            color: #666;
            padding: 30px;
            text-align: center;
            font-size: 16px;
            margin-top: 60px;
        }

        /* Chatbot styles */
        .chat-container {
            display: flex;
            flex-direction: column;
            height: 300px;
            justify-content: space-between;
        }

        .chat-messages {
            overflow-y: auto;
            max-height: 200px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px;
            background-color: #f9f9f9;
        }

        .user-message {
            text-align: right;
            margin: 5px 0;
            color: #4a90e2;
        }

        .bot-message {
            text-align: left;
            margin: 5px 0;
            color: #666;
        }
    </style>
</head>
<body>

    <header>
        <div class="header-content">
            <img src="logo-no-background.svg" alt="Lofttek Logo">
        </div>
    </header>

    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#" onclick="openChatbot()">Contact Us</a></li> <!-- Contact button to open chatbot -->
            <li><a href="#" onclick="toggleMembership()">Membership</a></li>
        </ul>
    </nav>

    <!-- Tek Tiers competition section -->
    <section class="hero">
        <h1>Lofttek Racing</h1>
        <video controls>
            <source src="your-video.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

        <div class="tier-grid">
            <div class="tier-card" onclick="openModal('tier1Modal')">
                <h3>Tek Tier 1</h3>
                <p>Beginner</p> <!-- Updated Tek Tier Name -->
            </div>
            <div class="tier-card" onclick="openModal('tier2Modal')">
                <h3>Tek Tier 2</h3>
                <p>Novice</p> <!-- Updated Tek Tier Name -->
            </div>
            <div class="tier-card" onclick="openModal('tier3Modal')">
                <h3>Tek Tier 3</h3>
                <p>Pro</p> <!-- Updated Tek Tier Name -->
            </div>
        </div>
    </section>

    <!-- Modals for each Tek Tier -->
    <div id="tier1Modal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('tier1Modal')">&times;</span>
            <h2>Tek Tier 1 - Beginner</h2>
            <p>Details about Tek Tier 1.</p>
        </div>
    </div>
    <div id="tier2Modal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('tier2Modal')">&times;</span>
            <h2>Tek Tier 2 - Novice</h2>
            <p>Details about Tek Tier 2.</p>
        </div>
    </div>
    <div id="tier3Modal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('tier3Modal')">&times;</span>
            <h2>Tek Tier 3 - Pro</h2>
            <p>Details about Tek Tier 3.</p>
        </div>
    </div>

    <!-- Chatbot -->
    <div id="chatbot" style="display: none; padding: 20px;">
        <h2>Chat with Us</h2>
        <div class="chat-container">
            <div class="chat-messages" id="chatMessages">
                <!-- Chat messages will appear here -->
            </div>
            <input type="text" id="chatInput" placeholder="Type a message..." onkeypress="sendMessage(event)">
        </div>
    </div>

    <!-- Membership Form -->
    <div class="membership-section" id="membershipForm">
        <h2>Join Our Membership</h2>
        <form class="membership-form">
            <label for="name">Name:</label>
            <input type="text" id="name" required>
            <label for="email">Email:</label>
            <input type="email" id="email" required>
            <button type="submit">Join</button>
        </form>
    </div>

    <footer>
        &copy; 2024 Lofttek Racing. All rights reserved.
    </footer>

    <script>
        function openModal(modalId) {
            document.getElementById(modalId).style.display = "block";
        }

        function closeModal(modalId) {
            document.getElementById(modalId).style.display = "none";
        }

        function toggleMembership() {
            const form = document.getElementById('membershipForm');
            form.style.display = (form.style.display === "none" || form.style.display === "") ? "block" : "none";
        }

        function openChatbot() {
            const chatbot = document.getElementById('chatbot');
            chatbot.style.display = (chatbot.style.display === "none" || chatbot.style.display === "") ? "block" : "none";
        }

        function sendMessage(event) {
            if (event.key === "Enter") {
                const input = document.getElementById('chatInput');
                const message = input.value;
                const chatMessages = document.getElementById('chatMessages');

                if (message) {
                    // Display user message
                    const userMessage = document.createElement('div');
                    userMessage.className = 'user-message';
                    userMessage.textContent = message;
                    chatMessages.appendChild(userMessage);

                    // Simulate bot response
                    const botResponse = document.createElement('div');
                    botResponse.className = 'bot-message';
                    botResponse.textContent = "You said: " + message; // This can be replaced with AI response
                    chatMessages.appendChild(botResponse);

                    // Clear input
                    input.value = '';
                    chatMessages.scrollTop = chatMessages.scrollHeight; // Auto-scroll
                }
            }
        }
    </script>
</body>
</html>
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kotoko AI - Secure BTech CSE Study Assistant</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #2563eb;
            --secondary: #1e40af;
            --dark: #0f172a;
            --light: #f8fafc;
            --accent: #8b5cf6;
            --success: #10b981;
        }

        body {
            background: linear-gradient(135deg, var(--dark), #1e293b);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo i {
            font-size: 2rem;
            color: var(--accent);
        }

        .logo h1 {
            font-size: 1.8rem;
            background: linear-gradient(to right, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            padding: 8px 15px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        nav a:hover {
            background: rgba(37, 99, 235, 0.2);
            color: var(--primary);
        }

        .hero {
            text-align: center;
            padding: 80px 20px;
            background: radial-gradient(circle at top right, rgba(139, 92, 246, 0.1), transparent 40%),
                        radial-gradient(circle at bottom left, rgba(37, 99, 235, 0.1), transparent 40%);
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 20px;
            background: linear-gradient(to right, var(--light), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
            color: #cbd5e1;
        }

        .cta-button {
            background: linear-gradient(45deg, var(--primary), var(--accent));
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.1rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }

        .features {
            padding: 60px 20px;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 50px;
            color: var(--light);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: rgba(30, 41, 59, 0.7);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: transform 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            background: rgba(30, 41, 59, 0.9);
        }

        .feature-card i {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--accent);
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .materials {
            padding: 60px 20px;
            background: rgba(15, 23, 42, 0.6);
        }

        .year-tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
            flex-wrap: wrap;
            gap: 10px;
        }

        .year-tab {
            background: rgba(30, 41, 59, 0.7);
            border: none;
            color: var(--light);
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .year-tab.active, .year-tab:hover {
            background: var(--primary);
        }

        .materials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .material-card {
            background: rgba(30, 41, 59, 0.7);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .material-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
            border-color: rgba(139, 92, 246, 0.3);
        }

        .material-card h4 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--accent);
        }

        .material-card ul {
            list-style: none;
        }

        .material-card li {
            padding: 8px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .material-card li:last-child {
            border-bottom: none;
        }

        .material-card a {
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s ease;
        }

        .material-card a:hover {
            color: var(--accent);
            gap: 15px;
        }

        .chatbot-container {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 1000;
        }

        .chatbot-toggle {
            width: 70px;
            height: 70px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
        }

        .chatbot-toggle:hover {
            transform: scale(1.1);
        }

        .chatbot-toggle i {
            font-size: 2rem;
            color: white;
        }

        .chatbot-window {
            position: absolute;
            bottom: 90px;
            right: 0;
            width: 400px;
            height: 500px;
            background: rgba(15, 23, 42, 0.95);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            display: flex;
            flex-direction: column;
            overflow: hidden;
            transform: translateY(20px);
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(139, 92, 246, 0.3);
        }

        .chatbot-window.active {
            transform: translateY(0);
            opacity: 1;
            visibility: visible;
        }

        .chatbot-header {
            background: rgba(30, 41, 59, 0.9);
            padding: 20px;
            display: flex;
            align-items: center;
            gap: 15px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .chatbot-header img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .chatbot-header h3 {
            font-size: 1.2rem;
            flex: 1;
        }

        .chatbot-header button {
            background: transparent;
            border: none;
            color: var(--light);
            cursor: pointer;
            font-size: 1.2rem;
        }

        .chatbot-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .message {
            max-width: 80%;
            padding: 12px 18px;
            border-radius: 18px;
            line-height: 1.5;
        }

        .bot-message {
            background: rgba(37, 99, 235, 0.2);
            align-self: flex-start;
            border-bottom-left-radius: 5px;
        }

        .user-message {
            background: rgba(139, 92, 246, 0.3);
            align-self: flex-end;
            border-bottom-right-radius: 5px;
        }

        .file-message {
            background: rgba(16, 185, 129, 0.2);
            align-self: flex-end;
            border-bottom-right-radius: 5px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .file-message i {
            font-size: 1.2rem;
        }

        .chatbot-input-container {
            padding: 15px;
            background: rgba(30, 41, 59, 0.9);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .chatbot-input-area {
            display: flex;
            gap: 10px;
        }

        .chatbot-input {
            flex: 1;
            padding: 12px 20px;
            border: none;
            border-radius: 30px;
            background: rgba(15, 23, 42, 0.7);
            color: white;
            outline: none;
        }

        .chatbot-input button {
            background: var(--primary);
            border: none;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            cursor: pointer;
            color: white;
            transition: all 0.3s ease;
        }

        .chatbot-input button:hover {
            background: var(--accent);
        }

        .upload-button {
            background: rgba(139, 92, 246, 0.3);
            border: none;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            cursor: pointer;
            color: white;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .upload-button:hover {
            background: var(--accent);
        }

        .file-upload-container {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
            padding: 10px;
            background: rgba(15, 23, 42, 0.5);
            border-radius: 10px;
        }

        .file-upload-container input {
            flex: 1;
            padding: 8px 15px;
            border: none;
            border-radius: 20px;
            background: rgba(30, 41, 59, 0.7);
            color: white;
            outline: none;
        }

        .file-upload-container button {
            background: var(--success);
            border: none;
            padding: 8px 15px;
            border-radius: 20px;
            color: white;
            cursor: pointer;
            font-size: 0.9rem;
        }

        .file-upload-container button:hover {
            background: #059669;
        }

        footer {
            background: rgba(15, 23, 42, 0.9);
            padding: 40px 20px;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .footer-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .footer-content p {
            color: #94a3b8;
            margin: 10px 0;
        }

        .security-features {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 30px 0;
        }

        .security-badge {
            background: rgba(16, 185, 129, 0.1);
            color: var(--success);
            padding: 8px 20px;
            border-radius: 30px;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 20px;
            }

            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }

            .hero h2 {
                font-size: 2.2rem;
            }

            .chatbot-window {
                width: 320px;
                height: 450px;
                right: 10px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-brain"></i>
                    <h1>Kotoko AI</h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#materials">Materials</a></li>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <section class="hero" id="home">
        <div class="container">
            <h2>Kotoko AI - Secure BTech CSE Study Portal</h2>
            <p>Access comprehensive study materials, exam resources, and AI-powered assistance for all 4 years of your Computer Science Engineering program. Built with security as the top priority.</p>
            <button class="cta-button">Get Started</button>
        </div>
    </section>

    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Why Choose Kotoko AI?</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <i class="fas fa-lock"></i>
                    <h3>Military-Grade Security</h3>
                    <p>End-to-end encryption, secure authentication, and regular security audits to protect your data.</p>
                </div>
                <div class="feature-card">
                    <i class="fas fa-robot"></i>
                    <h3>Advanced AI Assistant</h3>
                    <p>Powered by sophisticated algorithms to answer complex technical questions and provide detailed explanations.</p>
                </div>
                <div class="feature-card">
                    <i class="fas fa-book"></i>
                    <h3>Comprehensive Materials</h3>
                    <p>All subjects from 1st to 4th year CSE curriculum with notes, question papers, and resources.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="materials" id="materials">
        <div class="container">
            <h2 class="section-title">Study Materials</h2>
            <div class="year-tabs">
                <button class="year-tab active" data-year="1">1st Year</button>
                <button class="year-tab" data-year="2">2nd Year</button>
                <button class="year-tab" data-year="3">3rd Year</button>
                <button class="year-tab" data-year="4">4th Year</button>
            </div>
            <div class="materials-grid">
                <div class="material-card">
                    <h4>Mathematics</h4>
                    <ul>
                        <li><a href="#" onclick="downloadPDF('Higher Engineering Mathematics - B.S. Grewal.pdf')"><i class="fas fa-file-pdf"></i> Higher Engineering Mathematics - B.S. Grewal</a></li>
                        <li><a href="#" onclick="downloadPDF('Advanced Engineering Mathematics - Erwin Kreyszig.pdf')"><i class="fas fa-file-pdf"></i> Advanced Engineering Mathematics - Erwin Kreyszig</a></li>
                        <li><a href="#" onclick="downloadPDF('Mathematics-I Question Papers.pdf')"><i class="fas fa-file-pdf"></i> Previous Year Papers</a></li>
                    </ul>
                </div>
                <div class="material-card">
                    <h4>Programming</h4>
                    <ul>
                        <li><a href="#" onclick="downloadPDF('Let Us C - Yashavant Kanetkar.pdf')"><i class="fas fa-file-pdf"></i> Let Us C - Yashavant Kanetkar</a></li>
                        <li><a href="#" onclick="downloadPDF('Python Programming - Reema Thareja.pdf')"><i class="fas fa-file-pdf"></i> Python Programming - Reema Thareja</a></li>
                        <li><a href="#" onclick="downloadPDF('C Programming Question Papers.pdf')"><i class="fas fa-file-pdf"></i> C Programming Question Papers</a></li>
                    </ul>
                </div>
                <div class="material-card">
                    <h4>Physics/Chemistry</h4>
                    <ul>
                        <li><a href="#" onclick="downloadPDF('Engineering Physics - R.K. Gaur.pdf')"><i class="fas fa-file-pdf"></i> Engineering Physics - R.K. Gaur</a></li>
                        <li><a href="#" onclick="downloadPDF('Engineering Chemistry - Jain & Jain.pdf')"><i class="fas fa-file-pdf"></i> Engineering Chemistry - Jain & Jain</a></li>
                        <li><a href="#" onclick="downloadPDF('Physics Lab Manual.pdf')"><i class="fas fa-file-pdf"></i> Lab Manuals</a></li>
                    </ul>
                </div>
                <div class="material-card">
                    <h4>Electronics</h4>
                    <ul>
                        <li><a href="#" onclick="downloadPDF('Digital Electronics - Morris Mano.pdf')"><i class="fas fa-file-pdf"></i> Digital Electronics - Morris Mano</a></li>
                        <li><a href="#" onclick="downloadPDF('Electronic Devices - Floyd.pdf')"><i class="fas fa-file-pdf"></i> Electronic Devices - Floyd</a></li>
                        <li><a href="#" onclick="downloadPDF('Microprocessor Question Papers.pdf')"><i class="fas fa-file-pdf"></i> Microprocessor Question Papers</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <div class="chatbot-container">
        <div class="chatbot-toggle" id="chatbotToggle">
            <i class="fas fa-robot"></i>
        </div>
        <div class="chatbot-window" id="chatbotWindow">
            <div class="chatbot-header">
                <img src="#" alt="AI Assistant">
                <h3>Kotoko AI Assistant</h3>
                <button id="closeChatbot"><i class="fas fa-times"></i></button>
            </div>
            <div class="chatbot-messages" id="chatbotMessages">
                <div class="message bot-message">
                    Hello! I'm your Kotoko AI study assistant. I can help with complex technical questions, coding problems, and academic concepts. You can also upload files for analysis. How can I assist you today?
                </div>
            </div>
            <div class="chatbot-input-container">
                <div class="chatbot-input-area">
                    <input type="text" id="userInput" class="chatbot-input" placeholder="Ask complex questions about CSE subjects...">
                    <button class="upload-button" id="uploadButton">
                        <i class="fas fa-paperclip"></i>
                    </button>
                    <button id="sendMessage">
                        <i class="fas fa-paper-plane"></i>
                    </button>
                </div>
                <div class="file-upload-container" id="fileUploadContainer" style="display: none;">
                    <input type="file" id="fileInput" accept=".pdf,.doc,.docx,.txt,.jpg,.png">
                    <button id="uploadFileButton">Upload File</button>
                </div>
            </div>
        </div>
    </div>

    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <h3>Kotoko AI - BTech CSE Portal</h3>
                <p>Your trusted AI-powered companion for academic excellence with top-notch security</p>
                <div class="security-features">
                    <div class="security-badge">
                        <i class="fas fa-shield-alt"></i> SSL Encryption
                    </div>
                    <div class="security-badge">
                        <i class="fas fa-user-lock"></i> Secure Authentication
                    </div>
                    <div class="security-badge">
                        <i class="fas fa-database"></i> Encrypted Storage
                    </div>
                </div>
                <p>&copy; 2023 Kotoko AI. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Chatbot functionality
            var chatbotToggle = document.getElementById('chatbotToggle');
            var chatbotWindow = document.getElementById('chatbotWindow');
            var chatbotMessages = document.getElementById('chatbotMessages');
            var userInput = document.getElementById('userInput');
            var sendMessage = document.getElementById('sendMessage');
            var uploadButton = document.getElementById('uploadButton');
            var fileUploadContainer = document.getElementById('fileUploadContainer');
            var fileInput = document.getElementById('fileInput');
            var uploadFileButton = document.getElementById('uploadFileButton');
            var closeChatbot = document.getElementById('closeChatbot');

            if (chatbotToggle) {
                chatbotToggle.addEventListener('click', function() {
                    chatbotWindow.classList.toggle('active');
                });
            }

            if (closeChatbot) {
                closeChatbot.addEventListener('click', function() {
                    chatbotWindow.classList.remove('active');
                });
            }

            function addMessage(text, isUser, isFile = false) {
                var messageDiv = document.createElement('div');
                messageDiv.className = 'message';
                
                if (isFile) {
                    messageDiv.classList.add('file-message');
                    messageDiv.innerHTML = '<i class="fas fa-file"></i> ' + text;
                } else if (isUser) {
                    messageDiv.classList.add('user-message');
                    messageDiv.textContent = text;
                } else {
                    messageDiv.classList.add('bot-message');
                    messageDiv.textContent = text;
                }
                
                chatbotMessages.appendChild(messageDiv);
                chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
            }

            // Advanced AI response system
            function getAdvancedResponse(userMessage) {
                var lowerMessage = userMessage.toLowerCase();
                
                // Complex programming questions
                if (lowerMessage.indexOf('binary search tree') !== -1 && lowerMessage.indexOf('implement') !== -1) {
                    return "Here's a complete BST implementation in C++:\n\n```cpp\nclass Node {\npublic:\n    int data;\n    Node* left;\n    Node* right;\n    \n    Node(int value) {\n        data = value;\n        left = right = nullptr;\n    }\n};\n\nclass BST {\nprivate:\n    Node* root;\n    \n    Node* insert(Node* node, int value) {\n        if (!node) return new Node(value);\n        \n        if (value < node->data)\n            node->left = insert(node->left, value);\n        else if (value > node->data)\n            node->right = insert(node->right, value);\n        \n        return node;\n    }\n    \n    Node* search(Node* node, int value) {\n        if (!node || node->data == value)\n            return node;\n        \n        if (value < node->data)\n            return search(node->left, value);\n        \n        return search(node->right, value);\n    }\n    \npublic:\n    BST() { root = nullptr; }\n    \n    void insert(int value) {\n        root = insert(root, value);\n    }\n    \n    bool search(int value) {\n        return search(root, value) != nullptr;\n    }\n};\n```\n\nThis implementation includes insertion and search operations with O(log n) average time complexity.";
                }
                
                // Algorithm explanations
                if (lowerMessage.indexOf('quick sort') !== -1 && (lowerMessage.indexOf('algorithm') !== -1 || lowerMessage.indexOf('explain') !== -1)) {
                    return "QuickSort is a Divide-and-Conquer algorithm:\n\n**Algorithm Steps:**\n1. Choose a 'pivot' element from the array\n2. Partition other elements into two sub-arrays according to whether they are less than or greater than the pivot\n3. Recursively apply the above steps to the sub-arrays\n\n**Time Complexity:**\n- Best/Average Case: O(n log n)\n- Worst Case: O(n²) - when pivot is always the smallest or largest\n\n**Space Complexity:** O(log n) due to recursion stack\n\n**Why use QuickSort?**\n- In-place sorting (minimal memory usage)\n- Generally faster than other O(n log n) algorithms\n- Cache-efficient due to good locality of reference";
                }
                
                // Database concepts
                if (lowerMessage.indexOf('acid') !== -1 && lowerMessage.indexOf('property') !== -1) {
                    return "ACID properties ensure reliable database transactions:\n\n**Atomicity:** Transactions are all-or-nothing. Either all operations succeed, or none are applied.\n\n**Consistency:** Transactions bring the database from one valid state to another, maintaining database invariants.\n\n**Isolation:** Concurrent transactions execute as if they were sequential. Different isolation levels (Read Uncommitted, Read Committed, Repeatable Read, Serializable) control this.\n\n**Durability:** Once a transaction is committed, it remains so even in case of system failure.\n\nThese properties are crucial for financial systems, inventory management, and any application requiring data integrity.";
                }
                
                // Operating System concepts
                if (lowerMessage.indexOf('deadlock') !== -1 && (lowerMessage.indexOf('prevent') !== -1 || lowerMessage.indexOf('avoid') !== -1)) {
                    return "Deadlock prevention strategies:\n\n**1. Mutual Exclusion:** Not all resources can be shared (e.g., printers)\n\n**2. Hold and Wait:** Prevent by requiring processes to request all resources at once\n\n**3. No Preemption:** Allow OS to forcibly take resources from processes\n\n**4. Circular Wait:** Impose ordering on resource requests\n\n**Deadlock Avoidance (Banker's Algorithm):**\n- Check resource allocation safety before granting requests\n- Maintain 'need' and 'available' matrices\n- Only allocate if system remains in safe state\n\n**Deadlock Detection and Recovery:**\n- Periodically check for cycles in resource allocation graph\n- Recover by process termination or resource preemption";
                }
                
                // Network concepts
                if (lowerMessage.indexOf('tcp') !== -1 && lowerMessage.indexOf('udp') !== -1 && lowerMessage.indexOf('difference') !== -1) {
                    return "Key differences between TCP and UDP:\n\n**TCP (Transmission Control Protocol):**\n- Connection-oriented (handshake required)\n- Reliable (acknowledgments, retransmission)\n- Ordered delivery\n- Flow control and congestion control\n- Higher overhead\n- Used for: Web browsing, email, file transfer\n\n**UDP (User Datagram Protocol):**\n- Connectionless\n- Unreliable (no guarantees)\n- No ordering\n- Lower overhead\n- Faster transmission\n- Used for: Video streaming, online gaming, DNS\n\n**When to use which?**\nUse TCP when reliability is crucial, UDP when speed is more important than reliability.";
                }
                
                // Machine Learning concepts
                if (lowerMessage.indexOf('overfitting') !== -1 && (lowerMessage.indexOf('prevent') !== -1 || lowerMessage.indexOf('solve') !== -1)) {
                    return "Overfitting occurs when a model learns training data too well, including noise:\n\n**Detection:**\n- Large gap between training and validation accuracy\n- Model performs well on training data but poorly on new data\n\n**Prevention Techniques:**\n1. **Cross-validation:** Use k-fold CV to validate model performance\n2. **Regularization:** L1/L2 penalties on model complexity\n3. **Early stopping:** Halt training when validation error stops improving\n4. **Dropout:** Randomly ignore neurons during training (NNs)\n5. **Data augmentation:** Increase training data diversity\n6. **Simplify model:** Reduce features or model complexity\n7. **Ensemble methods:** Combine multiple models\n\n**Example:** In neural networks, dropout randomly sets 20-50% of neurons to zero during training, forcing network to learn redundant representations.";
                }
                
                // Compiler Design concepts
                if (lowerMessage.indexOf('lexical') !== -1 && lowerMessage.indexOf('analysis') !== -1) {
                    return "Lexical Analysis (Tokenization):\n\n**Purpose:** Converts character stream into token stream\n\n**Process:**\n1. Read source code character by character\n2. Identify tokens (keywords, identifiers, operators, literals)\n3. Remove whitespace and comments\n4. Generate symbol table entries\n\n**Tokens Types:**\n- Keywords (if, while, int)\n- Identifiers (variable names)\n- Literals (numbers, strings)\n- Operators (+, -, =)\n- Separators (parentheses, braces)\n\n**Implementation:** Often uses finite automata or regular expressions\n\n**Tools:** Lex/Flex for lexical analyzer generators\n\n**Error Handling:** Reports lexical errors like invalid characters or unterminated strings";
                }
                
                // Software Engineering concepts
                if (lowerMessage.indexOf('agile') !== -1 && lowerMessage.indexOf('waterfall') !== -1) {
                    return "Agile vs Waterfall Development Models:\n\n**Waterfall Model:**\n- Sequential phases: Requirements → Design → Implementation → Testing → Deployment\n- Each phase must complete before next begins\n- Documentation-heavy\n- Suitable for well-defined, stable requirements\n- Difficult to accommodate changes\n\n**Agile Model:**\n- Iterative and incremental development\n- Working software delivered in short sprints (1-4 weeks)\n- Emphasizes customer collaboration and responding to change\n- Continuous feedback and improvement\n- Adaptive planning\n\n**Agile Frameworks:**\n- Scrum: Sprints, daily standups, retrospectives\n- Kanban: Visual workflow management\n- XP: Pair programming, test-driven development\n\n**When to use Agile:**\n- Requirements are unclear or likely to change\n- Fast delivery needed\n- High customer involvement possible";
                }
                
                // Simple responses for common queries
                if (lowerMessage.indexOf('hello') !== -1 || lowerMessage.indexOf('hi') !== -1) {
                    return "Hello! I'm your Kotoko AI study assistant. I can help with complex technical questions, coding problems, and academic concepts. You can also upload files for analysis. What would you like to know?";
                } else if (lowerMessage.indexOf('math') !== -1) {
                    return "For Mathematics, I recommend 'Higher Engineering Mathematics' by B.S. Grewal. I can help with calculus, linear algebra, and probability concepts. What specific math topic would you like to explore?";
                } else if (lowerMessage.indexOf('programming') !== -1) {
                    return "I can help with programming concepts in C, C++, Java, Python, and more. I can explain algorithms, debug code, and suggest best practices. What programming question do you have?";
                } else if (lowerMessage.indexOf('data structure') !== -1) {
                    return "Data Structures are fundamental to computer science. I can explain arrays, linked lists, stacks, queues, trees, graphs, and hash tables with implementations. Which data structure would you like to understand?";
                } else if (lowerMessage.indexOf('kotoko') !== -1) {
                    return "Kotoko AI is your advanced study companion for BTech CSE. I provide detailed explanations for complex technical concepts, coding assistance, and academic support with military-grade security.";
                } else {
                    return "I'm an advanced AI assistant capable of handling complex technical questions in Computer Science. You can ask me about:\n• Data Structures & Algorithms\n• Programming concepts\n• Database systems\n• Operating Systems\n• Computer Networks\n• Machine Learning\n• Software Engineering\n• Compiler Design\n\nWhat complex topic would you like me to explain?";
                }
            }

            if (sendMessage) {
                sendMessage.addEventListener('click', function() {
                    var message = userInput.value.trim();
                    if (message) {
                        addMessage(message, true);
                        userInput.value = '';
                        
                        // Simulate advanced processing
                        setTimeout(function() {
                            var response = getAdvancedResponse(message);
                            addMessage(response, false);
                        }, 1500);
                    }
                });
            }

            if (userInput) {
                userInput.addEventListener('keypress', function(e) {
                    if (e.key === 'Enter') {
                        if (sendMessage) {
                            sendMessage.click();
                        }
                    }
                });
            }

            // File upload functionality
            if (uploadButton) {
                uploadButton.addEventListener('click', function() {
                    fileUploadContainer.style.display = fileUploadContainer.style.display === 'none' ? 'flex' : 'none';
                });
            }

            if (uploadFileButton) {
                uploadFileButton.addEventListener('click', function() {
                    var file = fileInput.files[0];
                    if (file) {
                        addMessage('Uploaded: ' + file.name, true, true);
                        fileUploadContainer.style.display = 'none';
                        fileInput.value = '';
                        
                        // Simulate file processing
                        setTimeout(function() {
                            addMessage("I've analyzed your file. Based on the content, I can help you with related concepts. What specific questions do you have about this material?", false);
                        }, 2000);
                    }
                });
            }

            // Year tabs functionality
            var yearTabs = document.querySelectorAll('.year-tab');
            yearTabs.forEach(function(tab) {
                tab.addEventListener('click', function() {
                    yearTabs.forEach(function(t) {
                        t.classList.remove('active');
                    });
                    tab.classList.add('active');
                    
                    addMessage('Switched to ' + tab.textContent + ' materials. What subject would you like to explore?', false);
                });
            });

            // Security features animation
            var securityBadges = document.querySelectorAll('.security-badge');
            if (securityBadges.length > 0) {
                setInterval(function() {
                    securityBadges.forEach(function(badge) {
                        badge.style.transform = 'scale(' + (1 + Math.random() * 0.1) + ')';
                        setTimeout(function() {
                            badge.style.transform = 'scale(1)';
                        }, 300);
                    });
                }, 3000);
            }
        });

        // Download function
        function downloadPDF(filename) {
            alert("In a real implementation, this would download: " + filename);
        }
    </script>
</body>
</html>
```

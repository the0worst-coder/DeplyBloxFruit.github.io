
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blox Fruits - Ultimate Adventure</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        orange: {
                            400: '#fb923c',
                            500: '#f97316',
                            600: '#ea580c'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .glow-orange {
            box-shadow: 0 0 20px rgba(249, 115, 22, 0.3);
        }
        .glow-pink {
            box-shadow: 0 0 20px rgba(236, 72, 153, 0.3);
        }
        .backdrop-blur {
            backdrop-filter: blur(8px);
        }
    </style>
</head>
<body class="bg-gray-900">
    <!-- Landing Page -->
    <div id="landingPage" class="min-h-screen relative" style="background-image: url('https://tse4.mm.bing.net/th/id/OIP.chtrj3RK5XWmy3WDRCU5sgHaEK?rs=1&pid=ImgDetMain&o=7&rm=3'); background-size: cover; background-position: center;">
        <div class="absolute inset-0 bg-slate-900/80"></div>
        
        <!-- Navigation -->
        <nav class="relative z-10 bg-slate-900/95 backdrop-blur border-b border-orange-500/30">
            <div class="container mx-auto px-4 py-4">
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-2">
                        <div class="w-8 h-8 bg-orange-500 rounded-full flex items-center justify-center glow-orange">
                            <span class="text-white font-bold">⚔</span>
                        </div>
                        <span class="text-xl font-bold text-white">Blox Fruits</span>
                    </div>
                    <button onclick="showAuthDialog()" class="bg-transparent border-2 border-orange-500 text-white px-6 py-2 rounded-lg hover:bg-orange-500/20 glow-orange transition-all duration-300">
                        Join Adventure
                    </button>
                </div>
            </div>
        </nav>

        <!-- Hero Section -->
        <div class="relative z-10 flex items-center justify-center min-h-screen text-center px-4">
            <div class="max-w-4xl">
                <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 drop-shadow-2xl">
                    Join the Ultimate
                    <span class="text-orange-400">Blox Fruits</span>
                    Adventure
                </h1>
                <p class="text-xl md:text-2xl text-white/90 mb-8 drop-shadow-lg">
                    Discover legendary Devil Fruits, master powerful abilities, and become the strongest pirate in the seas
                </p>
                <button onclick="showAuthDialog()" class="bg-orange-500 hover:bg-orange-600 text-white px-8 py-4 rounded-lg text-lg font-semibold glow-orange transition-all duration-300">
                    Start Your Journey
                </button>
            </div>
        </div>
    </div>

    <!-- Auth Dialog -->
    <div id="authDialog" class="fixed inset-0 bg-black/50 backdrop-blur flex items-center justify-center z-50 hidden">
        <div class="bg-slate-900 border border-orange-500/30 rounded-lg p-6 w-full max-w-md mx-4 aspect-square flex flex-col justify-center">
            <div id="authContent">
                <!-- Login Form -->
                <div id="loginForm">
                    <h2 class="text-2xl font-bold text-white mb-6 text-center">Welcome Back, Pirate!</h2>
                    <form onsubmit="handleLogin(event)">
                        <div class="space-y-4">
                            <input type="text" id="loginUsername" placeholder="Username" required class="w-full p-3 bg-slate-800 border border-slate-600 rounded-lg text-white placeholder-gray-400 focus:border-orange-500 focus:outline-none">
                            <input type="password" id="loginPassword" placeholder="Password" required class="w-full p-3 bg-slate-800 border border-slate-600 rounded-lg text-white placeholder-gray-400 focus:border-orange-500 focus:outline-none">
                            <button type="submit" class="w-full bg-orange-500 hover:bg-orange-600 text-white py-3 rounded-lg font-semibold glow-orange transition-all duration-300">
                                Set Sail
                            </button>
                        </div>
                    </form>
                    <p class="text-center text-gray-400 mt-4">
                        New to the seas? 
                        <button onclick="showSignupForm()" class="text-orange-400 hover:text-orange-300">Create Account</button>
                    </p>
                </div>

                <!-- Signup Form -->
                <div id="signupForm" class="hidden">
                    <h2 class="text-2xl font-bold text-white mb-6 text-center">Join the Crew!</h2>
                    <form onsubmit="handleSignup(event)">
                        <div class="space-y-4">
                            <input type="text" id="signupUsername" placeholder="Choose Username" required class="w-full p-3 bg-slate-800 border border-slate-600 rounded-lg text-white placeholder-gray-400 focus:border-orange-500 focus:outline-none">
                            <input type="password" id="signupPassword" placeholder="Create Password" required class="w-full p-3 bg-slate-800 border border-slate-600 rounded-lg text-white placeholder-gray-400 focus:border-orange-500 focus:outline-none">
                            <input type="text" id="signupProfile" placeholder="Profile Description (Optional)" class="w-full p-3 bg-slate-800 border border-slate-600 rounded-lg text-white placeholder-gray-400 focus:border-orange-500 focus:outline-none">
                            <button type="submit" class="w-full bg-orange-500 hover:bg-orange-600 text-white py-3 rounded-lg font-semibold glow-orange transition-all duration-300">
                                Begin Adventure
                            </button>
                        </div>
                    </form>
                    <p class="text-center text-gray-400 mt-4">
                        Already have an account? 
                        <button onclick="showLoginForm()" class="text-orange-400 hover:text-orange-300">Sign In</button>
                    </p>
                </div>
            </div>
        </div>
    </div>

    <!-- Dashboard -->
    <div id="dashboard" class="min-h-screen relative hidden" style="background-image: url('https://tse4.mm.bing.net/th/id/OIP.ketJPWa8bEgJyXzWf130UwHaEK?rs=1&pid=ImgDetMain&o=7&rm=3'); background-size: cover; background-position: center;">
        <div class="absolute inset-0 bg-slate-900/70 backdrop-blur"></div>
        
        <!-- Header -->
        <header class="relative z-10 border-b border-white/20 bg-black/30 backdrop-blur">
            <div class="container mx-auto px-4 py-4">
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-6">
                        <div class="flex items-center space-x-2">
                            <div class="w-8 h-8 bg-orange-500 rounded-full flex items-center justify-center glow-orange">
                                <span class="text-white font-bold">⚔</span>
                            </div>
                            <span class="text-xl font-bold text-white">Blox Fruits</span>
                        </div>
                        <!-- Added more spacing with space-x-6 and mr-6 -->
                        <div class="bg-slate-800/90 text-white border border-white/20 px-3 py-1 rounded-full text-xs mr-6">
                            Made by Lec, fairs, benson, rage And The Dev Team
                        </div>
                    </div>

                    <div class="flex items-center space-x-4">
                        <button onclick="window.open('https://www.tiktok.com/@lec0f', '_blank')" class="bg-transparent border border-pink-500/50 text-white px-4 py-2 rounded-lg hover:bg-pink-500/20 hover:border-pink-500 glow-pink transition-all duration-300">
                            Owner TikTok
                        </button>
                        <div class="flex items-center space-x-2">
                            <div class="w-8 h-8 bg-orange-500 rounded-full flex items-center justify-center text-white font-bold" id="userAvatar">
                                U
                            </div>
                            <span class="text-sm font-medium text-white" id="username">User</span>
                        </div>
                        <button onclick="handleLogout()" class="bg-transparent border border-orange-500/50 text-white px-4 py-2 rounded-lg hover:bg-orange-500/20 hover:border-orange-500 glow-orange transition-all duration-300">
                            Logout
                        </button>
                    </div>
                </div>
            </div>
        </header>

        <!-- Main Content -->
        <div class="relative z-10 container mx-auto px-4 py-6">
            <!-- Tabs -->
            <div class="bg-black/30 backdrop-blur border border-white/20 rounded-lg p-1 mb-6">
                <div class="grid grid-cols-3 gap-1">
                    <button onclick="showTab('chat')" id="chatTab" class="tab-button active px-4 py-2 rounded-lg text-white transition-all duration-300">
                        💬 Chat
                    </button>
                    <button onclick="showTab('server')" id="serverTab" class="tab-button px-4 py-2 rounded-lg text-white/80 hover:text-white transition-all duration-300">
                        🔗 BloxFruits Private Server
                    </button>
                    <button onclick="showTab('credits')" id="creditsTab" class="tab-button px-4 py-2 rounded-lg text-white/80 hover:text-white transition-all duration-300">
                        🏆 Credits
                    </button>
                </div>
            </div>

            <!-- Chat Tab -->
            <div id="chatContent" class="tab-content">
                <div class="bg-black/40 backdrop-blur border border-white/20 rounded-lg p-6">
                    <div class="flex items-center space-x-2 mb-4">
                        <h2 class="text-xl font-bold text-white">Global Chat</h2>
                        <div class="bg-green-600/90 text-white px-2 py-1 rounded-full text-xs border border-green-500/30">
                            Live
                        </div>
                    </div>
                    <p class="text-white/70 mb-4">Connect with pirates from around the world</p>
                    
                    <div class="border border-white/20 rounded-lg p-4 bg-black/20 backdrop-blur h-96 overflow-y-auto mb-4" id="chatMessages">
                        <!-- Chat messages will be populated by JavaScript -->
                    </div>

                    <form onsubmit="handleSendMessage(event)" class="flex space-x-2">
                        <input type="text" id="chatInput" placeholder="Type your message..." class="flex-1 p-3 bg-black/30 border border-white/20 rounded-lg text-white placeholder-white/50 focus:border-orange-500/50 focus:outline-none">
                        <button type="submit" class="bg-transparent border border-orange-500/50 text-white px-4 py-3 rounded-lg hover:bg-orange-500/20 hover:border-orange-500 glow-orange transition-all duration-300">
                            ➤
                        </button>
                    </form>
                </div>
            </div>

            <!-- Server Tab -->
            <div id="serverContent" class="tab-content hidden">
                <div class="bg-black/40 backdrop-blur border border-white/20 rounded-lg p-6">
                    <div class="flex items-center space-x-2 mb-4">
                        <h2 class="text-xl font-bold text-white">BloxFruits Private Server</h2>
                        <div class="bg-orange-500/20 text-orange-400 px-2 py-1 rounded-full text-xs border border-orange-500/30">
                            Exclusive
                        </div>
                    </div>
                    <p class="text-white/70 mb-6">Join our exclusive private server for the ultimate Blox Fruits experience</p>
                    
                    <div class="text-center space-y-6">
                        <div class="w-16 h-16 bg-orange-500/20 rounded-full flex items-center justify-center mx-auto glow-orange">
                            <span class="text-orange-400 text-2xl">👥</span>
                        </div>
                        <div>
                            <h3 class="text-lg font-semibold text-white">Exclusive Private Server Access</h3>
                            <p class="text-white/70">Experience Blox Fruits like never before with our premium private server</p>
                            <p class="text-orange-400 font-medium mt-2">
                                You might have a chance to find the owner Lec of the website and get a good perm
                            </p>
                        </div>

                        <div class="grid md:grid-cols-2 gap-4 max-w-md mx-auto">
                            <div class="bg-black/30 border border-white/20 rounded-lg p-4">
                                <div class="text-2xl font-bold text-orange-400">24/7</div>
                                <div class="text-sm text-white/70">Server Uptime</div>
                            </div>
                            <div class="bg-black/30 border border-white/20 rounded-lg p-4">
                                <div class="text-2xl font-bold text-orange-400">2x</div>
                                <div class="text-sm text-white/70">XP & Drop Rates</div>
                            </div>
                        </div>

                        <button onclick="window.open('https://shorturl.asia/Cw03u', '_blank')" class="bg-transparent border-2 border-orange-500 text-white px-8 py-3 rounded-lg hover:bg-orange-500/20 glow-orange transition-all duration-300 font-semibold">
                            🔗 Join Private Server
                        </button>
                        <p class="text-xs text-white/50">Click to access our exclusive private server</p>
                    </div>
                </div>
            </div>

            <!-- Credits Tab -->
            <div id="creditsContent" class="tab-content hidden">
                <div class="bg-black/40 backdrop-blur border border-white/20 rounded-lg p-6 max-w-md mx-auto aspect-square">
                    <div class="flex items-center space-x-2 mb-4">
                        <h2 class="text-xl font-bold text-white">Credits</h2>
                        <span class="text-orange-400">🏆</span>
                    </div>
                    <p class="text-white/70 mb-4">Meet the team behind this amazing website</p>
                    
                    <div class="h-80 overflow-y-auto space-y-4">
                        <div class="bg-black/30 rounded-lg p-4 border border-white/20">
                            <h3 class="text-white font-semibold mb-2">UI Design</h3>
                            <p class="text-orange-400">fairs</p>
                            <p class="text-white/70 text-sm">Created the beautiful user interface</p>
                        </div>

                        <div class="bg-black/30 rounded-lg p-4 border border-white/20">
                            <h3 class="text-white font-semibold mb-2">Authentication System</h3>
                            <p class="text-orange-400">The Dev Team</p>
                            <p class="text-white/70 text-sm">Built the login and signup functionality</p>
                        </div>

                        <div class="bg-black/30 rounded-lg p-4 border border-white/20">
                            <h3 class="text-white font-semibold mb-2">Chat System</h3>
                            <p class="text-orange-400">benson</p>
                            <p class="text-white/70 text-sm">Developed the live chat feature</p>
                        </div>

                        <div class="bg-black/30 rounded-lg p-4 border border-white/20">
                            <h3 class="text-white font-semibold mb-2">Server Integration</h3>
                            <p class="text-orange-400">rage</p>
                            <p class="text-white/70 text-sm">Connected the private server functionality</p>
                        </div>

                        <div class="bg-black/30 rounded-lg p-4 border border-white/20">
                            <h3 class="text-white font-semibold mb-2">Project Lead & Owner</h3>
                            <p class="text-orange-400">Lec</p>
                            <p class="text-white/70 text-sm">Visionary behind the entire project</p>
                        </div>

                        <div class="bg-black/30 rounded-lg p-4 border border-white/20">
                            <h3 class="text-white font-semibold mb-2">Special Thanks</h3>
                            <p class="text-orange-400">The Dev Team</p>
                            <p class="text-white/70 text-sm">Additional development and support</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Chat messages data
        let chatMessages = [
            {
                id: 1,
                user: "David",
                message: "Just got the Rubber fruit! This is amazing!",
                timestamp: "2 min ago",
                isBot: true
            },
            {
                id: 2,
                user: "Shadow",
                message: "Nice! I just mastered a new sword technique with the Dark fruit",
                timestamp: "1 min ago",
                isBot: true
            },
            {
                id: 3,
                user: "Naruto",
                message: "Anyone want to team up for the next raid? I have the Phoenix fruit!",
                timestamp: "30 sec ago",
                isBot: true
            }
        ];

        let currentUser = null;

        // Bot messages and users
        const botMessages = [
            "Just defeated a Sea Beast with my Magma fruit! Got some rare loot!",
            "Looking for crew members for tomorrow's raid, I have the Ice fruit",
            "The new update is incredible! Love the new Buddha fruit abilities",
            "Anyone know where to find the legendary sword? My Light fruit isn't enough",
            "Just reached max level with my Rubber fruit! Time to help newbies",
            "The PvP arena is so intense today! My Fire fruit is burning everyone!",
            "Found a secret island with amazing treasures using my Portal fruit!",
            "Training my Haki skills with the Dragon fruit, getting stronger every day!",
            "My Quake fruit just destroyed an entire island! So powerful!",
            "Anyone trading fruits? I have an extra Leopard fruit",
            "The Dough fruit combo is insane! Just wiped a whole crew",
            "My Venom fruit poison is spreading everywhere in PvP!",
            "Just awakened my String fruit! The damage is incredible",
            "Shadow fruit teleportation saved me from that Sea King!",
            "My Gravity fruit is pulling everyone into my combos!"
        ];

        const botUsers = [
            "David", "Shadow", "Naruto", "Alex", "Luna", "Phoenix", 
            "Blade", "Storm", "Ace", "Zara", "Kai", "Nova", "Rex", "Maya", "Frost"
        ];

        // Initialize
        window.onload = function() {
            const savedUser = localStorage.getItem('bloxfruits_current_user');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                showDashboard();
            }
            renderChatMessages();
            
            // Start bot message interval (every hour)
            setInterval(addBotMessage, 3600000);
        };

        // Auth functions
        function showAuthDialog() {
            document.getElementById('authDialog').classList.remove('hidden');
        }

        function hideAuthDialog() {
            document.getElementById('authDialog').classList.add('hidden');
        }

        function showLoginForm() {
            document.getElementById('loginForm').classList.remove('hidden');
            document.getElementById('signupForm').classList.add('hidden');
        }

        function showSignupForm() {
            document.getElementById('loginForm').classList.add('hidden');
            document.getElementById('signupForm').classList.remove('hidden');
        }

        function handleLogin(event) {
            event.preventDefault();
            const username = document.getElementById('loginUsername').value;
            const password = document.getElementById('loginPassword').value;
            
            const savedUser = localStorage.getItem(`bloxfruits_user_${username}`);
            if (savedUser) {
                const userData = JSON.parse(savedUser);
                if (userData.password === password) {
                    currentUser = userData;
                    localStorage.setItem('bloxfruits_current_user', JSON.stringify(currentUser));
                    showDashboard();
                    hideAuthDialog();
                } else {
                    alert('Invalid password!');
                }
            } else {
                alert('User not found!');
            }
        }

        function handleSignup(event) {
            event.preventDefault();
            const username = document.getElementById('signupUsername').value;
            const password = document.getElementById('signupPassword').value;
            const profile = document.getElementById('signupProfile').value;
            
            const userData = {
                username: username,
                password: password,
                profile: profile || 'A brave pirate on an adventure!',
                createdAt: new Date().toISOString()
            };
            
            localStorage.setItem(`bloxfruits_user_${username}`, JSON.stringify(userData));
            currentUser = userData;
            localStorage.setItem('bloxfruits_current_user', JSON.stringify(currentUser));
            showDashboard();
            hideAuthDialog();
        }

        function handleLogout() {
            localStorage.removeItem('bloxfruits_current_user');
            currentUser = null;
            document.getElementById('dashboard').classList.add('hidden');
            document.getElementById('landingPage').classList.remove('hidden');
        }

        function showDashboard() {
            document.getElementById('landingPage').classList.add('hidden');
            document.getElementById('dashboard').classList.remove('hidden');
            document.getElementById('username').textContent = currentUser.username;
            document.getElementById('userAvatar').textContent = currentUser.username[0].toUpperCase();
        }

        // Tab functions
        function showTab(tabName) {
            // Hide all tab contents
            document.querySelectorAll('.tab-content').forEach(content => {
                content.classList.add('hidden');
            });
            
            // Remove active class from all tabs
            document.querySelectorAll('.tab-button').forEach(button => {
                button.classList.remove('active', 'bg-orange-500/30', 'glow-orange');
                button.classList.add('text-white/80');
            });
            
            // Show selected tab content
            document.getElementById(tabName + 'Content').classList.remove('hidden');
            
            // Add active class to selected tab
            const activeTab = document.getElementById(tabName + 'Tab');
            activeTab.classList.add('active', 'bg-orange-500/30', 'glow-orange');
            activeTab.classList.remove('text-white/80');
            activeTab.classList.add('text-white');
        }

        // Chat functions
        function renderChatMessages() {
            const chatContainer = document.getElementById('chatMessages');
            chatContainer.innerHTML = '';
            
            chatMessages.forEach(msg => {
                const messageDiv = document.createElement('div');
                messageDiv.className = 'flex items-start space-x-3 mb-3';
                messageDiv.innerHTML = `
                    <div class="w-8 h-8 ${msg.isBot ? 'bg-blue-600' : 'bg-orange-600'} rounded-full flex items-center justify-center text-white font-bold">
                        ${msg.user[0].toUpperCase()}
                    </div>
                    <div class="flex-1 space-y-1">
                        <div class="flex items-center space-x-2">
                            <span class="text-sm font-medium text-white">${msg.user}</span>
                            <span class="text-xs text-white/50">${msg.timestamp}</span>
                        </div>
                        <p class="text-sm ${msg.isError ? 'text-red-400 font-medium' : 'text-white/90'}">
                            ${msg.message}
                        </p>
                    </div>
                `;
                chatContainer.appendChild(messageDiv);
            });
            
            chatContainer.scrollTop = chatContainer.scrollHeight;
        }

        function handleSendMessage(event) {
            event.preventDefault();
            const input = document.getElementById('chatInput');
            const message = input.value.trim();
            
            if (!message) return;
            
            const newMessage = {
                id: Date.now(),
                user: currentUser.username,
                message: "Opps.. you need to join the private server first!",
                timestamp: "now",
                isBot: false,
                isError: true
            };
            
            chatMessages.push(newMessage);
            if (chatMessages.length > 20) {
                chatMessages = chatMessages.slice(-20);
            }
            
            renderChatMessages();
            input.value = '';
        }

        function addBotMessage() {
            const randomUser = botUsers[Math.floor(Math.random() * botUsers.length)];
            const randomMessage = botMessages[Math.floor(Math.random() * botMessages.length)];
            
            const newMessage = {
                id: Date.now(),
                user: randomUser,
                message: randomMessage,
                timestamp: "now",
                isBot: true
            };
            
            chatMessages.push(newMessage);
            if (chatMessages.length > 20) {
                chatMessages = chatMessages.slice(-20);
            }
            
            renderChatMessages();
        }

        // Initialize chat tab as active
        document.addEventListener('DOMContentLoaded', function() {
            showTab('chat');
        });
    </script>
</body>
</html>

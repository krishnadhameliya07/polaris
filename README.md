# polaris
Author - Krishna Dhameliya

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Stellar Coders Club</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- Load Inter Font -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Custom scroll behavior for smooth scrolling on internal links */
        html {
            scroll-behavior: smooth;
        }
    </style>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'primary-dark': '#111827',
                        'secondary-dark': '#1F2937',
                        'accent-cyan': '#06B6D4',
                        'accent-purple': '#8B5CF6',
                    }
                }
            }
        }

        // Function to toggle mobile menu (optional interaction)
        function toggleMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }
    </script>
</head>

<body class="bg-primary-dark text-gray-200">

    <!-- 1. Navbar -->
    <header class="sticky top-0 z-50 bg-secondary-dark/95 backdrop-blur-sm shadow-lg border-b border-accent-cyan/20">
        <nav class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo/Club Name -->
                <a href="#home" class="flex items-center space-x-2">
                    <i data-lucide="rocket" class="w-6 h-6 text-accent-cyan"></i>
                    <span class="text-xl font-bold text-white tracking-wider">Stellar Coders</span>
                </a>

                <!-- Desktop Menu -->
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="text-gray-300 hover:text-accent-cyan transition duration-300 font-medium">Home</a>
                    <a href="#about" class="text-gray-300 hover:text-accent-cyan transition duration-300 font-medium">About</a>
                    <a href="#events" class="text-gray-300 hover:text-accent-cyan transition duration-300 font-medium">Events</a>
                    <a href="#contact" class="text-gray-300 hover:text-accent-cyan transition duration-300 font-medium">Contact</a>
                </div>

                <!-- Mobile Menu Button -->
                <div class="md:hidden">
                    <button type="button" onclick="toggleMenu()" class="text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-accent-cyan rounded-md p-2">
                        <i data-lucide="menu" class="w-6 h-6"></i>
                    </button>
                </div>
            </div>
        </nav>

        <!-- Mobile Menu (Hidden by default) -->
        <div id="mobile-menu" class="md:hidden hidden">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="#home" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-base font-medium text-white hover:bg-secondary-dark/70">Home</a>
                <a href="#about" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-secondary-dark/70">About</a>
                <a href="#events" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-secondary-dark/70">Events</a>
                <a href="#contact" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-secondary-dark/70">Contact</a>
            </div>
        </div>
    </header>

    <main>
        <!-- 2. Hero Section -->
        <section id="home" class="py-24 md:py-36 text-center bg-primary-dark border-b-4 border-accent-cyan/30">
            <div class="max-w-4xl mx-auto px-4">
                <i data-lucide="cpu" class="w-20 h-20 text-accent-cyan mx-auto mb-6 animate-pulse"></i>
                <h1 class="text-5xl sm:text-7xl font-extrabold text-white mb-4 leading-tight">
                    The <span class="text-transparent bg-clip-text bg-gradient-to-r from-accent-cyan to-accent-purple">Stellar</span> Coders
                </h1>
                <p class="text-lg sm:text-xl text-gray-400 max-w-2xl mx-auto mb-8">
                    Launch your tech career. Build the future. Connect with the innovators of tomorrow.
                </p>
                <a href="#events" class="inline-flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-full shadow-lg text-white bg-accent-purple hover:bg-accent-purple/90 transition duration-300 transform hover:scale-105">
                    View Upcoming Events
                </a>
            </div>
        </section>

        <!-- 3. About Section -->
        <section id="about" class="py-16 md:py-24 bg-secondary-dark">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl font-bold text-center mb-12 text-white">About Our Mission</h2>
                <div class="bg-primary-dark p-8 md:p-12 rounded-xl shadow-2xl border border-accent-purple/30">
                    <p class="text-lg text-gray-300 leading-relaxed mb-6">
                        The Stellar Coders is a dynamic student organization dedicated to fostering a community of technology enthusiasts, developers, and designers. We believe in learning by doing, which is why our focus is heavily on hands-on projects, workshops, and hackathons. Whether you're a seasoned programmer or just writing your first 'Hello World,' you'll find a supportive environment here to grow your skills and network.
                    </p>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center mt-10">
                        <div class="p-4 rounded-lg bg-secondary-dark/50 hover:bg-secondary-dark transition duration-300">
                            <i data-lucide="code" class="w-8 h-8 text-accent-cyan mx-auto mb-3"></i>
                            <h3 class="text-xl font-semibold text-white">Hands-On Workshops</h3>
                            <p class="text-sm text-gray-400">Master new languages and frameworks weekly.</p>
                        </div>
                        <div class="p-4 rounded-lg bg-secondary-dark/50 hover:bg-secondary-dark transition duration-300">
                            <i data-lucide="users" class="w-8 h-8 text-accent-cyan mx-auto mb-3"></i>
                            <h3 class="text-xl font-semibold text-white">Collaborative Projects</h3>
                            <p class="text-sm text-gray-400">Build real-world applications with peers.</p>
                        </div>
                        <div class="p-4 rounded-lg bg-secondary-dark/50 hover:bg-secondary-dark transition duration-300">
                            <i data-lucide="award" class="w-8 h-8 text-accent-cyan mx-auto mb-3"></i>
                            <h3 class="text-xl font-semibold text-white">Competitive Hackathons</h3>
                            <p class="text-sm text-gray-400">Test your skills and win prizes annually.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. Events Section -->
        <section id="events" class="py-16 md:py-24 bg-primary-dark">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl font-bold text-center mb-12 text-white">Upcoming Missions (Events)</h2>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <!-- Event Card 1 -->
                    <div class="bg-secondary-dark p-6 rounded-xl shadow-xl hover:shadow-accent-cyan/20 transition duration-300 border-t-4 border-accent-cyan">
                        <span class="block text-sm font-semibold text-accent-cyan mb-2">OCT 28</span>
                        <h3 class="text-2xl font-bold text-white mb-3">React Fundamentals Workshop</h3>
                        <p class="text-gray-400 mb-4">A crash course on building interactive user interfaces with React Hooks.</p>
                        <div class="flex items-center text-sm text-gray-300 space-x-4">
                            <span class="flex items-center"><i data-lucide="clock" class="w-4 h-4 mr-2"></i> 6:00 PM - 8:00 PM</span>
                            <span class="flex items-center"><i data-lucide="map-pin" class="w-4 h-4 mr-2"></i> Engineering Hall, Room 301</span>
                        </div>
                    </div>

                    <!-- Event Card 2 -->
                    <div class="bg-secondary-dark p-6 rounded-xl shadow-xl hover:shadow-accent-cyan/20 transition duration-300 border-t-4 border-accent-purple">
                        <span class="block text-sm font-semibold text-accent-purple mb-2">NOV 10</span>
                        <h3 class="text-2xl font-bold text-white mb-3">Annual Code Comet Hackathon</h3>
                        <p class="text-gray-400 mb-4">24 hours of intense coding, problem-solving, and free pizza! Register now.</p>
                        <div class="flex items-center text-sm text-gray-300 space-x-4">
                            <span class="flex items-center"><i data-lucide="clock" class="w-4 h-4 mr-2"></i> All Day</span>
                            <span class="flex items-center"><i data-lucide="map-pin" class="w-4 h-4 mr-2"></i> University Auditorium</span>
                        </div>
                    </div>

                    <!-- Event Card 3 -->
                    <div class="bg-secondary-dark p-6 rounded-xl shadow-xl hover:shadow-accent-cyan/20 transition duration-300 border-t-4 border-accent-cyan">
                        <span class="block text-sm font-semibold text-accent-cyan mb-2">NOV 25</span>
                        <h3 class="text-2xl font-bold text-white mb-3">Intro to AI/ML with Python</h3>
                        <p class="text-gray-400 mb-4">Explore the basics of machine learning using popular Python libraries.</p>
                        <div class="flex items-center text-sm text-gray-300 space-x-4">
                            <span class="flex items-center"><i data-lucide="clock" class="w-4 h-4 mr-2"></i> 7:00 PM - 9:00 PM</span>
                            <span class="flex items-center"><i data-lucide="map-pin" class="w-4 h-4 mr-2"></i> Online via Zoom</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. Contact Section -->
        <section id="contact" class="py-16 md:py-24 bg-secondary-dark">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl font-bold text-center mb-12 text-white">Get in Touch</h2>

                <div class="bg-primary-dark p-8 rounded-xl shadow-2xl border border-accent-purple/30">
                    <p class="text-lg text-gray-300 text-center mb-8">
                        Ready to join the mission? Send us a quick message or follow our social channels!
                    </p>

                    <!-- Dummy Contact Form (Frontend Only) -->
                    <form onsubmit="event.preventDefault(); showContactMessage();" class="space-y-6">
                        <div>
                            <label for="name" class="block text-sm font-medium text-gray-300 mb-2">Name</label>
                            <input type="text" id="name" name="name" required class="w-full px-4 py-3 bg-secondary-dark border border-gray-600 rounded-lg focus:ring-accent-cyan focus:border-accent-cyan text-white shadow-sm" placeholder="Your Name">
                        </div>
                        <div>
                            <label for="email" class="block text-sm font-medium text-gray-300 mb-2">Email</label>
                            <input type="email" id="email" name="email" required class="w-full px-4 py-3 bg-secondary-dark border border-gray-600 rounded-lg focus:ring-accent-cyan focus:border-accent-cyan text-white shadow-sm" placeholder="your.email@college.edu">
                        </div>
                        <div>
                            <label for="message" class="block text-sm font-medium text-gray-300 mb-2">Message</label>
                            <textarea id="message" name="message" rows="4" required class="w-full px-4 py-3 bg-secondary-dark border border-gray-600 rounded-lg focus:ring-accent-cyan focus:border-accent-cyan text-white shadow-sm" placeholder="Tell us how you'd like to contribute..."></textarea>
                        </div>
                        <button type="submit" class="w-full flex justify-center py-3 px-4 border border-transparent rounded-lg shadow-lg text-lg font-medium text-white bg-accent-cyan hover:bg-accent-cyan/90 transition duration-300 transform hover:scale-[1.01]">
                            Send Message
                        </button>
                    </form>

                    <div id="contact-message" class="mt-4 p-4 bg-green-900/50 text-green-300 rounded-lg hidden text-center">
                        Thank you for your interest! Since this is a static site, your message has not been sent, but we appreciate the contact.
                    </div>

                    <!-- Social Media Links -->
                    <div class="mt-10 pt-6 border-t border-gray-700 text-center">
                        <h3 class="text-xl font-semibold text-white mb-4">Find Us Online</h3>
                        <div class="flex justify-center space-x-6">
                            <!-- Placeholder for Instagram -->
                            <a href="#" class="text-gray-400 hover:text-accent-purple transition duration-300" aria-label="Instagram">
                                <i data-lucide="instagram" class="w-7 h-7"></i>
                            </a>
                            <!-- Placeholder for GitHub -->
                            <a href="#" class="text-gray-400 hover:text-accent-purple transition duration-300" aria-label="GitHub">
                                <i data-lucide="github" class="w-7 h-7"></i>
                            </a>
                            <!-- Placeholder for Discord -->
                            <a href="#" class="text-gray-400 hover:text-accent-purple transition duration-300" aria-label="Discord">
                                <i data-lucide="message-square" class="w-7 h-7"></i>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="bg-primary-dark border-t border-gray-800 py-6 text-center text-gray-500">
        <p>&copy; 2024 The Stellar Coders. All rights reserved. | Designed with Tailwind CSS.</p>
    </footer>

    <script>
        // Initialize Lucide icons
        lucide.createIcons();

        // Simple script to show a message after dummy form submission
        function showContactMessage() {
            const messageDiv = document.getElementById('contact-message');
            messageDiv.classList.remove('hidden');
            // Hide message after 5 seconds
            setTimeout(() => {
                messageDiv.classList.add('hidden');
            }, 5000);
        }
    </script>
</body>
</html>

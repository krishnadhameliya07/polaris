# polaris
Author - Krishna Dhameliya

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Neptune Network | Digital Creators Club</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- Load Inter Font -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            transition: background-color 0.3s, color 0.3s;
        }

        /* --- Custom CSS for Subtle Animations & Toast --- */
        
        /* 1. Keyframes for the Slow Float animation (Applied to the main icon) */
        @keyframes slow-float {
            0%, 100% {
                transform: translateY(0) rotate(0);
            }
            50% {
                transform: translateY(-5px) rotate(1deg);
            }
        }
        
        /* 2. Toast Animation */
        .toast-slide-in {
            animation: slideIn 0.3s forwards;
        }
        .toast-slide-out {
            animation: slideOut 0.3s forwards;
        }

        @keyframes slideIn {
            from { transform: translateY(100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes slideOut {
            from { transform: translateY(0); opacity: 1; }
            to { transform: translateY(100%); opacity: 0; }
        }

        html {
            scroll-behavior: smooth;
        }
        
        /* Custom Tooltip Styling using a pseudo-element for the arrow */
        .custom-tooltip-arrow::after {
            content: '';
            position: absolute;
            bottom: 100%; 
            left: 50%;
            transform: translateX(-50%);
            border-width: 5px;
            border-style: solid;
            border-color: transparent transparent #06B6D4 transparent; /* Arrow color is cyan-accent */
        }

        /* --- New Typewriter Animation Styles --- */

        /* 3. Typewriter Keyframes */
        @keyframes typing {
            from { width: 0 }
            to { width: 100% } 
        }
        
        /* 4. Blinking Cursor Keyframes */
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #06B6D4; } /* Use cyan-accent for the cursor */
        }

        /* 5. Typewriter Container and Text Styling */
        .typewriter-container {
            /* Ensures the animation wrapper is centered */
            width: fit-content; 
            white-space: nowrap; /* Prevents text from wrapping during animation */
            overflow: hidden; /* Clips the text before it is 'typed' */
            margin: 0 auto;
        }

        .typewriter-text {
            /* The 'cursor' is the right border, color-matched to cyan-accent */
            border-right: .15em solid #06B6D4; 
            width: 0; /* Starts at 0 width */
            /* Animation: 
               1. 'typing' animates the width using 21 steps, revealing text one character at a time.
               2. 'blink-caret' runs 4 times (3.0s total duration) starting after the 2.5s typing delay.
               3. 'forwards' on both ensures the text stays visible and the cursor remains transparent.
            */
            animation: 
                typing 2.5s steps(21, end) forwards, 
                blink-caret 3.0s step-end 4 2.5s forwards; 
            display: inline-block; /* Essential for width-based animation */
        }
    </style>
    <script>
        tailwind.config = {
            darkMode: 'class', // Enable class-based dark mode
            theme: {
                extend: {
                    colors: {
                        // Dark Mode Palette
                        'navy-base': '#08173E', // Primary background (Dark)
                        'navy-secondary': '#0E2758', // Card/Section background (Dark)
                        
                        // Accent Colors (Used in both modes for high contrast)
                        'electric-blue': '#4F46E5', /* Indigo/Violet for contrast */
                        'cyan-accent': '#06B6D4',

                        // Light Mode Palette (UPDATED to white-sky blue)
                        'light-base': '#F0F9FF', // Very pale sky blue
                        'light-secondary': '#FFFFFF', // Pure white
                        'dark-text': '#1F2937', // Primary text (Dark)
                    },
                    // Add custom animation timing
                    animation: {
                        'slow-float': 'slow-float 6s ease-in-out infinite',
                    },
                }
            }
        }

        // --- Core JavaScript Logic for Level 3 Interactivity ---

        // 1. Event Data Array (Replaces hardcoded HTML)
        const eventsData = [
            {
                date: "NOV 5",
                color: "cyan-accent",
                title: "Figma Basics: Wireframing",
                description: "Learn the essentials of rapid prototyping for web and mobile apps.",
                time: "5:30 PM",
                location: "Design Lab, Room 102"
            },
            {
                date: "NOV 18",
                color: "electric-blue",
                title: "LinkedIn & Portfolio Review",
                description: "Get professional critiques on your digital presence from alumni.",
                time: "7:00 PM",
                location: "Zoom Call (Link TBA)"
            },
            {
                date: "DEC 1",
                color: "cyan-accent",
                title: "Digital Marketing Workshop",
                description: "A deep dive into SEO, analytics, and content generation best practices.",
                time: "6:00 PM",
                location: "Business School, 4th Floor"
            },
            {
                date: "DEC 15",
                color: "electric-blue",
                title: "Semester Wrap-Up Social",
                description: "Celebrate a successful semester of networking and creation!",
                time: "6:30 PM",
                location: "Student Union Cafeteria"
            }
        ];

        // 2. Dynamic Event Rendering
        function renderEvents() {
            const container = document.getElementById('events-container');
            if (!container) return; 

            let htmlContent = '';
            eventsData.forEach(event => {
                // Determine card background and text colors based on the current theme
                const isDarkMode = document.body.classList.contains('dark');
                // Use light-secondary (white) for card background in light mode
                const bgColor = isDarkMode ? 'bg-navy-secondary' : 'bg-light-secondary'; 
                const titleColor = isDarkMode ? 'text-white' : 'text-dark-text'; 
                const descColor = isDarkMode ? 'text-gray-400' : 'text-gray-600'; 
                const detailColor = isDarkMode ? 'text-gray-300' : 'text-gray-500'; 
                // Enhanced hover effect: lift slightly (translate-y-1) and change shadow
                const shadowClass = isDarkMode 
                    ? `shadow-xl hover:shadow-2xl hover:shadow-${event.color}/30` 
                    : `shadow-lg hover:shadow-xl hover:shadow-gray-300`;

                htmlContent += `
                    <div class="${bgColor} p-6 rounded-xl ${shadowClass} transition duration-300 hover:-translate-y-1 border-t-4 border-${event.color}">
                        <span class="block text-sm font-semibold text-${event.color} mb-2">${event.date}</span>
                        <h3 class="text-2xl font-bold ${titleColor} mb-3">${event.title}</h3>
                        <p class="${descColor} mb-4">${event.description}</p>
                        <div class="flex flex-col sm:flex-row sm:items-center text-sm ${detailColor} space-y-2 sm:space-y-0 sm:space-x-4">
                            <span class="flex items-center"><i data-lucide="clock" class="w-4 h-4 mr-2"></i> ${event.time}</span>
                            <span class="flex items-center"><i data-lucide="map-pin" class="w-4 h-4 mr-2"></i> ${event.location}</span>
                        </div>
                    </div>
                `;
            });
            container.innerHTML = htmlContent;
            lucide.createIcons(); // Re-initialize icons after injecting new HTML
        }

        // 3. Footer Current Year Update
        function updateFooterYear() {
            const yearSpan = document.getElementById('current-year');
            // This function fetches the current year from the date object
            if (yearSpan) {
                yearSpan.textContent = new Date().getFullYear();
            }
        }

        // 4. Light/Dark Mode Toggle Logic
        function setTheme(isDark) {
            const body = document.body;
            const toggleIcon = document.getElementById('theme-toggle-icon');
            // Also update mobile toggle icon
            const toggleIconMobile = document.getElementById('theme-toggle-icon-mobile');

            if (isDark) {
                body.classList.add('dark');
                // Remove light mode classes
                body.classList.remove('bg-light-base', 'text-dark-text');
                // Ensure dark mode classes are active (already handled by dark: prefix, but good practice)
                body.classList.add('bg-navy-base', 'text-gray-100');
                localStorage.setItem('theme', 'dark');
                if (toggleIcon) toggleIcon.setAttribute('data-lucide', 'sun');
                if (toggleIconMobile) toggleIconMobile.setAttribute('data-lucide', 'sun');
            } else {
                body.classList.remove('dark');
                // Remove dark mode classes
                body.classList.remove('bg-navy-base', 'text-gray-100');
                // Apply light mode classes (sky-blue base background, dark text)
                body.classList.add('bg-light-base', 'text-dark-text');
                localStorage.setItem('theme', 'light');
                if (toggleIcon) toggleIcon.setAttribute('data-lucide', 'moon');
                if (toggleIconMobile) toggleIconMobile.setAttribute('data-lucide', 'moon');
            }

            renderEvents(); 
            lucide.createIcons(); 
        }

        function toggleTheme() {
            const isDark = document.body.classList.contains('dark');
            setTheme(!isDark);
        }

        // 5. Contact Form Logic with Toast Animation
        function showContactMessage() {
            event.preventDefault(); // Prevent form submission
            const toastDiv = document.getElementById('toast-message');
            const form = document.getElementById('contact-form');
            
            // Remove previous animation classes
            toastDiv.classList.remove('hidden', 'toast-slide-out');
            
            // Apply slide-in animation
            toastDiv.classList.add('toast-slide-in');

            // Clear the form fields
            form.reset(); 

            // Hide message after 4 seconds with slide-out animation
            setTimeout(() => {
                toastDiv.classList.remove('toast-slide-in');
                toastDiv.classList.add('toast-slide-out');
                
                // Fully hide after animation completes
                setTimeout(() => {
                    toastDiv.classList.add('hidden');
                }, 300);
            }, 4000);
        }

        // Navbar toggle for mobile
        function toggleMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // Initialization: Check stored theme and set up dynamic content
        window.onload = function() {
            // Check for saved theme preference
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme === 'light') {
                setTheme(false); // Set to light mode
            } else {
                setTheme(true); // Default to dark mode
            }

            updateFooterYear(); // Ensure this is called to set the year!
        }
    </script>
</head>

<!-- Body now defaults to light mode base colors, but is immediately overridden by setTheme in JS -->
<body class="bg-light-base text-dark-text dark:bg-navy-base dark:text-gray-100">

    <!-- Toast Notification (Fixed Position) -->
    <div id="toast-message" class="fixed bottom-0 right-0 m-4 p-4 rounded-lg shadow-2xl bg-green-700 text-white z-[9999] hidden border-l-4 border-green-300">
        <span class="font-bold">Success!</span> Your request has been sent to the network.
    </div>

    <!-- 1. Navbar -->
    <!-- Nav bar uses white background in light mode (light-secondary) and navy-base in dark mode -->
    <header class="sticky top-0 z-50 bg-light-secondary/95 dark:bg-navy-base/95 backdrop-blur-sm shadow-xl border-b border-cyan-accent/50 dark:border-cyan-accent/50">
        <nav class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo/Club Name -->
                <a href="#home" class="flex items-center space-x-2">
                    <i data-lucide="network" class="w-7 h-7 text-cyan-accent"></i>
                    <!-- Logo text is dark in light mode, white in dark mode -->
                    <span class="text-xl font-extrabold tracking-widest text-dark-text dark:text-white">NEPTUNE NETWORK</span>
                </a>

                <!-- Desktop Menu -->
                <div class="hidden md:flex items-center space-x-8">
                    <!-- Nav links are dark gray in light mode, light gray in dark mode -->
                    <a href="#home" class="text-gray-600 dark:text-gray-300 hover:text-electric-blue transition duration-300 font-medium">Home</a>
                    <a href="#about" class="text-gray-600 dark:text-gray-300 hover:text-electric-blue transition duration-300 font-medium">About</a>
                    <a href="#events" class="text-gray-600 dark:text-gray-300 hover:text-electric-blue transition duration-300 font-medium">Events</a>
                    <a href="#contact" class="text-gray-600 dark:text-gray-300 hover:text-electric-blue transition duration-300 font-medium">Connect</a>
                    
                    <!-- Theme Toggle Button -->
                    <button id="theme-toggle" onclick="toggleTheme()" class="text-gray-600 dark:text-gray-400 hover:text-cyan-accent p-2 rounded-full transition duration-300">
                        <i id="theme-toggle-icon" data-lucide="sun" class="w-6 h-6"></i>
                    </button>
                </div>

                <!-- Mobile Menu Button and Toggle -->
                <div class="md:hidden flex items-center space-x-2">
                    <!-- Theme Toggle Button (Mobile) -->
                    <button id="theme-toggle-mobile" onclick="toggleTheme()" class="text-gray-600 dark:text-gray-400 hover:text-cyan-accent p-2 rounded-full transition duration-300">
                        <i id="theme-toggle-icon-mobile" data-lucide="sun" class="w-6 h-6"></i>
                    </button>
                    <!-- Hamburger Menu -->
                    <button type="button" onclick="toggleMenu()" class="text-gray-600 dark:text-gray-400 hover:text-electric-blue focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-light-secondary dark:focus:ring-offset-navy-base focus:ring-cyan-accent rounded-md p-2">
                        <i data-lucide="menu" class="w-6 h-6"></i>
                    </button>
                </div>
            </div>
        </nav>

        <!-- Mobile Menu (Background is secondary color for contrast) -->
        <div id="mobile-menu" class="md:hidden hidden bg-light-base dark:bg-navy-secondary shadow-lg">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="#home" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-base font-medium text-dark-text dark:text-white hover:bg-light-secondary dark:hover:bg-navy-base/70">Home</a>
                <a href="#about" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-dark-text dark:text-gray-300 hover:bg-light-secondary dark:hover:bg-navy-base/70">About</a>
                <a href="#events" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-dark-text dark:text-gray-300 hover:bg-light-secondary dark:hover:bg-navy-base/70">Events</a>
                <a href="#contact" onclick="toggleMenu()" class="block px-3 py-2 rounded-md text-dark-text dark:text-gray-300 hover:bg-light-secondary dark:hover:bg-navy-base/70">Connect</a>
            </div>
        </div>
    </header>

    <main>
        <!-- 2. Hero Section - Primary Background (Sky Blue / Deep Navy) -->
        <section id="home" class="py-24 md:py-40 text-center bg-light-base dark:bg-navy-base transition-colors duration-300">
            <div class="max-w-4xl mx-auto px-4">
                <!-- Neptune logo element (a stylized ring) -->
                <div class="relative w-24 h-24 mx-auto mb-6">
                    <div class="absolute w-full h-full rounded-full border-4 border-electric-blue opacity-50 animate-ping"></div>
                    <!-- Apply slow-float animation to the icon -->
                    <i data-lucide="globe" class="absolute inset-0 w-full h-full p-2 text-cyan-accent animate-slow-float"></i>
                </div>

                <!-- Title text color is handled by body class / dark:text-white -->
                <h1 class="text-5xl sm:text-7xl font-extrabold mb-4 leading-tight">
                    <!-- Updated structure for Typewriter Animation -->
                    <div class="typewriter-container">
                        <span id="animated-title" class="typewriter-text text-dark-text dark:text-white">
                            The 
                            <!-- Apply gradient styling to "Neptune" -->
                            <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-accent to-electric-blue">Neptune</span> 
                            Network
                        </span>
                    </div>
                </h1>
                <p class="text-lg sm:text-xl text-gray-700 dark:text-gray-300 max-w-2xl mx-auto mb-8">
                    Connecting the next generation of designers, communicators, and digital innovators.
                </p>
                <!-- Added active:scale-95 and active:shadow-sm for a subtle press effect -->
                <a href="#about" class="inline-flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-full shadow-lg text-white bg-electric-blue hover:bg-electric-blue/90 transition duration-300 transform hover:scale-105 active:scale-95 active:shadow-sm ring-4 ring-electric-blue/30">
                    Discover Our Mission
                </a>
            </div>
        </section>

        <!-- 3. About Section - Secondary Background (White / Navy Secondary) -->
        <section id="about" class="py-16 md:py-24 bg-light-secondary dark:bg-navy-secondary transition-colors duration-300">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl font-bold text-center mb-12 text-dark-text dark:text-white">The Core Connection</h2>
                <!-- Inner Container - Primary Background (Sky Blue / Navy Base) -->
                <div class="bg-light-base dark:bg-navy-base p-8 md:p-12 rounded-xl shadow-2xl border border-electric-blue/40 transition-colors duration-300">
                    <p class="text-lg text-gray-700 dark:text-gray-300 leading-relaxed mb-6">
                        The Neptune Network is the campus hub for everything related to digital communication, UI/UX design, social media strategy, and professional networking. We bridge the gap between technical skill and creative strategy, providing members with the tools and connections needed to thrive in the modern digital landscape. Our goal is to create high-impact projects and build lasting professional relationships.
                    </p>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center mt-10">
                        <!-- Inner Cards - Secondary Background (White / Navy Secondary) -->
                        <!-- Added subtle hover:translate-y-1 and hover:shadow-xl -->
                        <div class="p-4 rounded-lg bg-light-secondary dark:bg-navy-secondary/70 hover:bg-gray-100 dark:hover:bg-navy-secondary transition duration-300 hover:-translate-y-1 hover:shadow-xl">
                            <i data-lucide="layers" class="w-8 h-8 text-cyan-accent mx-auto mb-3"></i>
                            <h3 class="text-xl font-semibold text-dark-text dark:text-white">Design Sprints</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">Collaborative UI/UX challenges.</p>
                        </div>
                        <div class="p-4 rounded-lg bg-light-secondary dark:bg-navy-secondary/70 hover:bg-gray-100 dark:hover:bg-navy-secondary transition duration-300 hover:-translate-y-1 hover:shadow-xl">
                            <i data-lucide="message-square-text" class="w-8 h-8 text-cyan-accent mx-auto mb-3"></i>
                            <h3 class="text-xl font-semibold text-dark-text dark:text-white">Communication Strategy</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">Mastering persuasive digital content.</p>
                        </div>
                        <div class="p-4 rounded-lg bg-light-secondary dark:bg-navy-secondary/70 hover:bg-gray-100 dark:hover:bg-navy-secondary transition duration-300 hover:-translate-y-1 hover:shadow-xl">
                            <i data-lucide="briefcase" class="w-8 h-8 text-cyan-accent mx-auto mb-3"></i>
                            <h3 class="text-xl font-semibold text-dark-text dark:text-white">Industry Connect</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">Guest speakers and portfolio reviews.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. Events Section - Primary Background (Sky Blue / Deep Navy) -->
        <section id="events" class="py-16 md:py-24 bg-light-base dark:bg-navy-base transition-colors duration-300">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl font-bold text-center mb-12 text-dark-text dark:text-white">Upcoming Transmissions (Events)</h2>

                <!-- Dynamic Content Container -->
                <div id="events-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Events will be injected here by the renderEvents() function -->
                    <p class="col-span-full text-center text-gray-500 dark:text-gray-400 italic">Loading events...</p>
                </div>
            </div>
        </section>

        <!-- 5. Contact Section - Secondary Background (White / Navy Secondary) -->
        <section id="contact" class="py-16 md:py-24 bg-light-secondary dark:bg-navy-secondary transition-colors duration-300">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-4xl font-bold text-center mb-12 text-dark-text dark:text-white">Join the Flow</h2>

                <!-- Inner Form Container - Primary Background (Sky Blue / Navy Base) -->
                <div class="bg-light-base dark:bg-navy-base p-8 rounded-xl shadow-2xl border border-electric-blue/40 transition-colors duration-300">
                    <p class="text-lg text-gray-700 dark:text-gray-300 text-center mb-8">
                        Ready to make an impact? Send a message to the core team or follow our digital channels.
                    </p>

                    <!-- Join the Club Form (Now with JS interaction) -->
                    <form id="contact-form" onsubmit="showContactMessage()" class="space-y-6">
                        <div>
                            <label for="name" class="block text-sm font-medium text-dark-text dark:text-gray-300 mb-2">Full Name</label>
                            <!-- Input with Recessed Shadow and Electric Blue Focus Ring -->
                            <input type="text" id="name" name="name" required class="w-full px-4 py-3 bg-light-secondary dark:bg-navy-secondary border border-gray-300 dark:border-gray-700 rounded-lg shadow-inner focus:ring-2 focus:ring-electric-blue focus:border-transparent text-dark-text dark:text-white transition duration-200" placeholder="Your Name">
                        </div>
                        <div>
                            <label for="email" class="block text-sm font-medium text-dark-text dark:text-gray-300 mb-2">College Email</label>
                            <!-- Input with Recessed Shadow and Electric Blue Focus Ring -->
                            <input type="email" id="email" name="email" required class="w-full px-4 py-3 bg-light-secondary dark:bg-navy-secondary border border-gray-300 dark:border-gray-700 rounded-lg shadow-inner focus:ring-2 focus:ring-electric-blue focus:border-transparent text-dark-text dark:text-white transition duration-200" placeholder="your.id@university.edu">
                        </div>
                        <div>
                            <label for="message" class="block text-sm font-medium text-dark-text dark:text-gray-300 mb-2">Inquiry</label>
                            <!-- Textarea with Recessed Shadow and Electric Blue Focus Ring -->
                            <textarea id="message" name="message" rows="4" required class="w-full px-4 py-3 bg-light-secondary dark:bg-navy-secondary border border-gray-300 dark:border-gray-700 rounded-lg shadow-inner focus:ring-2 focus:ring-electric-blue focus:border-transparent text-dark-text dark:text-white transition duration-200" placeholder="I'm interested in the design track!"></textarea>
                        </div>
                        <!-- Added active:scale-[0.99] and active:shadow-md for a subtle press effect -->
                        <button type="submit" class="w-full flex justify-center py-3 px-4 border border-transparent rounded-lg shadow-lg text-lg font-medium text-white bg-cyan-accent hover:bg-cyan-accent/90 transition duration-300 transform hover:scale-[1.01] active:scale-[0.99] active:shadow-md">
                            Send Transmission
                        </button>
                    </form>

                    <!-- Social Media Links -->
                    <div class="mt-10 pt-6 border-t border-gray-300 dark:border-gray-700 text-center">
                        <h3 class="text-xl font-semibold text-dark-text dark:text-white mb-4">Follow Our Signal</h3>
                        <div class="flex justify-center space-x-6">
                            
                            <!-- Instagram (Wrapped in group for custom tooltip) -->
                            <div class="relative group">
                                <a href="#" class="text-gray-600 dark:text-gray-400 hover:text-electric-blue transition duration-300 p-2 rounded-full block" aria-label="Instagram">
                                    <i data-lucide="instagram" class="w-7 h-7"></i>
                                </a>
                                <!-- Custom Tooltip: Changed to appear BELOW the icon -->
                                <span class="absolute top-full left-1/2 -translate-x-1/2 mt-2 px-3 py-1 text-xs text-white whitespace-nowrap bg-cyan-accent rounded-md opacity-0 group-hover:opacity-100 transition duration-300 pointer-events-none custom-tooltip-arrow">
                                    Observe Our Orbits
                                </span>
                            </div>

                            <!-- Dribbble (Wrapped in group for custom tooltip) -->
                            <div class="relative group">
                                <a href="#" class="text-gray-600 dark:text-gray-400 hover:text-electric-blue transition duration-300 p-2 rounded-full block" aria-label="Dribbble">
                                    <i data-lucide="layers-3" class="w-7 h-7"></i>
                                </a>
                                <!-- Custom Tooltip: Changed to appear BELOW the icon -->
                                <span class="absolute top-full left-1/2 -translate-x-1/2 mt-2 px-3 py-1 text-xs text-white whitespace-nowrap bg-cyan-accent rounded-md opacity-0 group-hover:opacity-100 transition duration-300 pointer-events-none custom-tooltip-arrow">
                                    Blueprint Archives
                                </span>
                            </div>

                            <!-- Email (Wrapped in group for custom tooltip) -->
                            <div class="relative group">
                                <a href="mailto:contact@neptunenetwork.edu" class="text-gray-600 dark:text-gray-400 hover:text-electric-blue transition duration-300 p-2 rounded-full block" aria-label="Direct Email for Queries">
                                    <i data-lucide="mail" class="w-7 h-7"></i>
                                </a>
                                <!-- Custom Tooltip: Changed to appear BELOW the icon -->
                                <span class="absolute top-full left-1/2 -translate-x-1/2 mt-2 px-3 py-1 text-xs text-white whitespace-nowrap bg-cyan-accent rounded-md opacity-0 group-hover:opacity-100 transition duration-300 pointer-events-none custom-tooltip-arrow">
                                    Hail the Command Deck
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer - Primary Background (Sky Blue / Deep Navy) -->
    <footer class="bg-light-base dark:bg-navy-base border-t border-gray-300 dark:border-gray-800 py-6 text-center text-gray-500 dark:text-gray-500 transition-colors duration-300">
        <!-- Changed the span content to be empty, relying fully on the JS function -->
        <p>&copy; <span id="current-year"></span> The Neptune Network. All rights reserved. | Design: Sky Blue & Deep Navy Theme.</p>
    </footer>

</body>
</html>


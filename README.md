# polaris
Author - Krishna Dhameliya

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Innova Club | Official Website</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="font-sans bg-gray-50 text-gray-800">

  <!-- Navbar -->
  <nav class="bg-white shadow-md fixed w-full top-0 z-10">
    <div class="max-w-6xl mx-auto px-4 py-3 flex justify-between items-center">
      <div class="text-2xl font-bold text-indigo-600">Innova Club</div>
      <div class="space-x-6 hidden md:flex">
        <a href="#home" class="hover:text-indigo-600">Home</a>
        <a href="#about" class="hover:text-indigo-600">About</a>
        <a href="#events" class="hover:text-indigo-600">Events</a>
        <a href="#contact" class="hover:text-indigo-600">Contact</a>
      </div>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="home" class="h-screen flex flex-col justify-center items-center text-center bg-gradient-to-r from-indigo-500 to-purple-600 text-white">
    <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Club Logo" class="w-24 mb-6">
    <h1 class="text-5xl font-bold mb-4">Innova Club</h1>
    <p class="text-xl mb-6">Where Ideas Meet Innovation</p>
    <a href="#about" class="bg-white text-indigo-600 px-6 py-3 rounded-full font-semibold hover:bg-gray-100 transition">Learn More</a>
  </section>

  <!-- About Section -->
  <section id="about" class="py-16 px-6 bg-white">
    <div class="max-w-5xl mx-auto text-center">
      <h2 class="text-3xl font-bold mb-6 text-indigo-600">About Us</h2>
      <p class="text-lg leading-relaxed">
        The <strong>Innova Club</strong> is a student-driven community passionate about technology, creativity, and teamwork. 
        We organize workshops, hackathons, and brainstorming sessions to encourage innovation and practical learning. 
        Our mission is to empower students to explore new ideas and transform them into impactful projects.
      </p>
    </div>
  </section>

  <!-- Events Section -->
  <section id="events" class="py-16 px-6 bg-gray-100">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="text-3xl font-bold mb-10 text-indigo-600">Upcoming Events</h2>
      <div class="grid md:grid-cols-3 gap-8">
        <div class="bg-white shadow-md p-6 rounded-xl">
          <h3 class="text-xl font-semibold mb-2">HackWave 2025</h3>
          <p class="text-gray-600 mb-2">📅 November 15, 2025</p>
          <p class="text-gray-700">A 24-hour coding challenge focused on AI-driven solutions.</p>
        </div>
        <div class="bg-white shadow-md p-6 rounded-xl">
          <h3 class="text-xl font-semibold mb-2">Design Sprint</h3>
          <p class="text-gray-600 mb-2">📅 December 2, 2025</p>
          <p class="text-gray-700">A fun event for creative thinkers to build user-friendly app prototypes.</p>
        </div>
        <div class="bg-white shadow-md p-6 rounded-xl">
          <h3 class="text-xl font-semibold mb-2">Tech Talks</h3>
          <p class="text-gray-600 mb-2">📅 January 10, 2026</p>
          <p class="text-gray-700">An inspiring guest lecture series featuring innovators and entrepreneurs.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="py-16 px-6 bg-white">
    <div class="max-w-5xl mx-auto text-center">
      <h2 class="text-3xl font-bold mb-6 text-indigo-600">Contact Us</h2>
      <p class="mb-8 text-gray-700">Got a question or want to join us? Reach out below!</p>
      
      <form class="max-w-md mx-auto space-y-4">
        <input type="text" placeholder="Your Name" class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-indigo-500">
        <input type="email" placeholder="Your Email" class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-indigo-500">
        <textarea placeholder="Your Message" class="w-full border rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-indigo-500" rows="4"></textarea>
        <button type="submit" class="bg-indigo-600 text-white px-6 py-2 rounded-lg hover:bg-indigo-700 transition">Send Message</button>
      </form>

      <div class="mt-10 space-x-6 text-2xl">
        <a href="#" class="text-indigo-500 hover:text-indigo-700">🌐</a>
        <a href="#" class="text-indigo-500 hover:text-indigo-700">📘</a>
        <a href="#" class="text-indigo-500 hover:text-indigo-700">📸</a>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-800 text-white py-4 text-center">
    © 2025 Innova Club | All Rights Reserved
  </footer>

</body>
</html>

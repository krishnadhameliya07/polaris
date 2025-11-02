# polaris
Author - Krishna Dhameliya

The Neptune Network website is a sleek, fully responsive, one-page application built using modern web standards (HTML, Tailwind CSS, and vanilla JavaScript). It functions as the digital hub for a student organization focused on digital creators and innovators.


Design and Aesthetics -->
The site adheres to a high-contrast, professional "Sky Blue & Deep Navy" theme.

Color Palette: The design uses deep navy blues (navy-base) for the dark background and a pale sky blue (light-base) for the light background, accented by Cyan (cyan-accent) and a vibrant Electric Blue (electric-blue).

Theme Toggle: A persistent Light/Dark Mode switch is available in the header. The user's preference is saved locally using localStorage, ensuring the theme is consistent across sessions.

Responsiveness: All layouts, including the navigation bar (which collapses into a hamburger menu) and the event grid, are fully responsive using Tailwind's utility classes.


Interactive Features -->
The site incorporates several JavaScript and CSS features to enhance the user experience:

Typewriter Animation (Hero): The main title, "The Neptune Network," features the requested CSS-driven typewriter effect. It works by animating the width property using steps(21, end) to reveal the text character by character over 2.5 seconds, followed by a delayed, blinking cursor animation that fades out, mimicking a terminal command line.

Toast Notifications: Instead of using intrusive alert() calls, submitting the contact form triggers a visually smooth, animated Toast Notification that slides up from the bottom-right corner to confirm the "transmission" was sent.

Dynamic Event Cards: The Events section is populated dynamically by JavaScript using the eventsData array. This allows the event cards to automatically update their background and text colors to match the current light or dark theme when the toggle is flipped.


Subtle Micro-Animations -->

The main logo features a slow float and ping animation to give it a futuristic, 'connected' feel.

Interactive elements like buttons and cards include subtle hover effects (scale, shadow changes, slight upward translation) to provide visual feedback.

Social media icons include custom CSS tooltips to label their function on hover.


Content Structure -->
The site is organized into four main sections, accessible via the sticky navigation bar:

Home (#home): Hero section with the animated title and primary call to action.

About (#about): Details the club's mission and three core activities: Design Sprints, Communication Strategy, and Industry Connect.

Events (#events): Displays four upcoming event cards with details like date, time, and location.

Contact (#contact): Contains the email signup form and links to social channels.

# DJS02 – Web Component: Podcast Preview
🎙️ Podcast App – Web Component: Podcast Preview
Overview

This project implements a reusable and encapsulated Web Component that displays a podcast preview card as part of a modular podcast application.
Each card is a custom HTML element created using the Custom Elements API (customElements.define()), following the Web Components standard.

The app dynamically generates podcast cards from a data source, displays detailed podcast information in a modal, and includes filters to sort and view content—all without third-party frameworks.

✨ Features
🧩 Custom Web Component (<podcast-card>)

Built with native JavaScript using customElements.define().

Uses Shadow DOM for encapsulated styles and markup.

Accepts data through attributes:

cover – podcast cover image

title – podcast name

genres – list of genre names

seasons – number of seasons

updated – last updated date

Completely stateless — all data is passed from the parent.

Dispatches a custom event (podcastSelected) when clicked, allowing the parent app to open a modal or take other actions.

🧠 Parent Application (index.js)

Dynamically renders multiple <podcast-card> elements.

Listens for podcastSelected events from the web component.

Opens a modal with full podcast details, including:

Title and cover image

Description and genres

Last updated date

All seasons and episodes from the data source

Provides modal open/close functionality and event handling.

🎚️ Filter Section

Added a responsive horizontal filter bar (<section class="filters">) to sort or filter podcasts.

Styled with flexbox for clean horizontal layout.

Includes dropdowns for filtering by genre and sorting by recency or popularity.

Fully responsive and visually integrated with the app’s theme.

💅 Modal Design

Displays complete podcast details in a user-friendly format.

Includes a close button (×) and closes on outside click.

Dynamically populated with podcast info, genres, and episodes.

🧰 Technical Details
Feature	Description
Custom Element	<podcast-card> created with customElements.define()
Encapsulation	Shadow DOM used for scoped styles
Data Flow	Stateless component with attributes from parent
Event System	Dispatches podcastSelected event on click
Modal Interaction	Managed by parent index.js
Filters	Horizontal flex-based filter UI
Styling	Responsive, modern CSS layout
🧱 Folder Structure
📦 podcast-app
 ┣ 📂 src
 ┃ ┣ 📂 components
 ┃ ┃ ┗ 📜 PodcastCard.js
 ┃ ┣ 📜 index.js
 ┃ ┗ 📜 data.js
 ┣ 📜 index.html
 ┣ 📜 styles.css
 ┗ 📜 README.md

🚀 How It Works

index.js loads podcast data and dynamically creates <podcast-card> elements.

Each <podcast-card> receives attributes for cover, title, genres, etc.

When a card is clicked, it dispatches a podcastSelected event.

The parent listens for this event and opens a modal with detailed information.

The modal displays all seasons and episodes for the selected podcast.

Users can filter podcasts using the filter bar.

🧠 Design Principles

Stateless Components — all state managed by the parent.

Encapsulation — Shadow DOM prevents style leakage.

Reusability — Components can be reused anywhere in the app.

Separation of Concerns — Component handles display, parent handles logic.

Accessible & Responsive — Works across devices and modern browsers.

Listening for Events
document.addEventListener('podcastSelected', (event) => {
  const selectedId = event.detail.id;
  // Open modal or trigger another app action
});

📝 JSDoc Example

Major functions and class methods are documented using JSDoc:

/**
 * Opens the modal and renders podcast details.
 * @param {Object} podcast - The selected podcast object.
 * @returns {void}
 */
function openModal(podcast) { ... }

🧩 Technologies Used

HTML5, CSS3, JavaScript (ES6+)

Custom Elements API

Shadow DOM

No frameworks or external libraries

✅ Deliverables

PodcastCard.js – reusable Web Component

index.html – demo page showcasing component integration

index.js – logic for rendering, modal, and event handling

data.js – structured dataset of podcasts, seasons, and episodes

styles.css – responsive global styles

README.md – project overview and documentation

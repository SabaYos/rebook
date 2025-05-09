ReBook - Used Book Exchange Platform
Overview
ReBook is a simple web application for exchanging used books, built as a proof-of-concept over one week (May 5–11, 2025). It features two main views: a Customer View for browsing books and submitting requests, and a Seller View for adding books and managing incoming requests. The app focuses on Arabic books, uses Jordanian cities for location filtering, and is deployed on GitHub Pages.
Live Demo: https://sabayos.github.io/rebook
Features

Customer View:
Browse a catalog of 20 Arabic books (loaded from books.json) with local images.
Add new books via the Seller View, which are stored in localStorage.
Submit a request for a book by providing name, contact, location (Amman, Irbid, Zarqa, Aqaba), and Book ID.
Input validation ensures the Book ID exists and fields are non-empty.


Seller View:
Add new books with title, description, price (in JOD), and optional image URL (saved to localStorage).
View incoming requests in a table with columns for Book ID, customer name, contact, location, status, and actions (Accept/Ignore).
Filter requests by city (e.g., highlight Amman requests in yellow).
Input validation ensures valid book details (e.g., positive price, non-empty title).


UI/UX:
Modern design with Roboto font, animations (fade-in for book cards), and hover effects (button scaling).
Mobile-responsive layout (stacked book cards, scrollable request table).


Data Management:
Static book data in books.json (20 Arabic books with images/bookX.jpg).
Dynamic data (new books, requests) stored in browser’s localStorage.



Setup Instructions
Local Setup

Clone the repository:git clone https://github.com/sabayos/rebook.git
cd rebook


Serve the project locally using Python’s HTTP server:python -m http.server 8000


Open your browser and navigate to:http://localhost:8000


Ensure the images folder and books.json are in the root directory alongside index.html.

Live Demo

Visit the deployed site: https://sabayos.github.io/rebook

Project Structure

index.html: Main application file with Customer and Seller Views.
books.json: Contains 20 Arabic books with local image paths (e.g., images/book1.jpg).
images/: Folder with book images (e.g., book1.jpg to book20.jpg).

Limitations

Data Persistence: The app uses localStorage to store new books and requests, which means data is browser-specific and clears if the browser storage is reset. A production version would require a backend (e.g., Node.js) and database (e.g., MongoDB) to persist data across users and devices.
Static Hosting: Deployed on GitHub Pages, which is static, so there’s no server-side processing (e.g., no direct writes to books.json).
Scalability: localStorage may slow down with very large datasets (e.g., thousands of books/requests). A production app would use a database for better performance.

Edge Cases Tested

Empty localStorage: Falls back to books.json books; request table shows as empty.
Large datasets: Tested with 50 requests—table loads efficiently, filtering works.
Invalid inputs: Alerts for non-existent Book IDs, negative prices, or empty fields.
Arabic text: Renders correctly for book titles, descriptions, and customer names.

Future Improvements

Add a backend to persist data and enable user authentication.
Implement search functionality for books.
Enhance styling with more animations or a theme toggle (light/dark mode).
Add support for more languages and currencies.

Author

Sabayos (GitHub: sabayos)
Project timeline: May 5–11, 2025

License
This project is open-source and available under the MIT License.

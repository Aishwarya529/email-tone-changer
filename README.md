# email-tone-changer
ToneCraft
ToneCraft is a web application that allows users to rewrite emails in different tones (e.g., professional, friendly, formal, casual, enthusiastic) using the Google Gemini API. The frontend is a single-page HTML application with a responsive design, and the backend is built with Express.js to handle API requests.
Features

Tone Selection: Choose from five tones to rewrite your email.
Email Rewriting: Paste an email and transform its tone with a single click.
Responsive Design: Clean, modern UI with consistent styling across devices.
Backend Integration: Uses Google Gemini API for natural language processing.

Tech Stack

Frontend: HTML, CSS, JavaScript
Backend: Node.js, Express.js
API: Google Gemini API
Dependencies: express, cors, dotenv, @google/generative-ai

Prerequisites

Node.js (v16 or higher)
npm (v8 or higher)
A Google Gemini API key (obtain from Google AI Studio)

Setup Instructions
1. Clone the Repository
git clone <your-repository-url>
cd tonecraft

2. Install Backend Dependencies
Navigate to the backend directory (where your Express server file is located) and install dependencies:
npm install express cors dotenv @google/generative-ai

3. Configure Environment Variables
Create a .env file in the backend directory with the following:
GEMINI_API_KEY=your-google-gemini-api-key
PORT=5000

Replace your-google-gemini-api-key with your actual Gemini API key.
4. Run the Backend
Start the Express server:
node server.js

The server will run on http://localhost:5000 (or the port specified in .env). You should see:
Server is running on port 5000

5. Serve the Frontend
Host the index.html file using a local server. You can use Python’s HTTP server or any static file server:
python -m http.server 8000

Open http://localhost:8000 in your browser to access the ToneCraft UI.
Usage

Select a Tone: Choose a tone (e.g., Professional, Friendly) from the radio buttons.
Enter Email: Paste or type your email into the textarea.
Rewrite Email: Click the "Rewrite with Tone" button.
View Result: The rewritten email appears in the preview section below.

Testing the Backend Connection
To verify the backend is connected:

Ensure the backend is running (http://localhost:5000).

Test the /api/generate endpoint using curl or Postman:
curl -X POST http://localhost:5000/api/generate -H "Content-Type: application/json" -d '{"prompt": "Test"}'


In the frontend, enter an email, select a tone, and click "Rewrite with Tone". Check the preview section for the rewritten email or error messages.


Troubleshooting

"Connection Error: Backend not reachable":
Ensure the backend is running on http://localhost:5000.
Verify the port in the frontend’s fetch URL matches the backend port.
Check for firewall or network issues.


"Backend Error: Prompt is required":
Ensure the email textarea isn’t empty.


Gemini API Errors:
Verify GEMINI_API_KEY is correct in .env.
Check Gemini API quotas or rate limits.


CORS Issues:
The backend includes cors middleware, but ensure frontend and backend domains/ports align if hosted separately.



Project Structure
tonecraft/
├── server.js          # Express backend server
├── index.html         # Frontend HTML with CSS and JavaScript
├── .env               # Environment variables (not tracked in git)
├── package.json       # Backend dependencies and scripts
└── README.md          # This file

Contributing
Feel free to submit issues or pull requests to improve ToneCraft. Ensure any changes maintain the existing design (colors, layout, and format) as specified in index.html.


# AI-Hackathon
1. How to Set It Up

a. Clone the Repository:

Use the command:
git clone <repository-url>
cd <repository-folder>

b. Install Dependencies:

Install the required Python libraries:
pip install flask twilio openai

c. Configure the Application:

Open the app.py file and replace placeholders with:
Twilio Credentials: Account SID, Auth Token, and Phone Number.
OpenAI API Key: Your API key from OpenAI.

d. Run the Server:
Start the Flask server:
python app.py
The server runs on http://127.0.0.1:5000 by default.

2. How to Use It
a. Initiate Calls:

Send a POST request to the /bulk_call endpoint with customer phone numbers in JSON format:
{
  "customers": [
    {"phone": "+1234567890"},
    {"phone": "+0987654321"}
  ]
}

b. Interact During Calls:

Customers answer the call and speak.
Twilio sends their speech to the /voice endpoint for processing.
The AI responds with dynamic, context-aware dialogue, which is converted to speech and played back to the customer.

3. Understanding the Architecture
   
a. Flask Server:
Manages API endpoints for initiating calls and handling customer interactions.

b. Twilio Integration:
Handles call setup, speech-to-text conversion, and text-to-speech playback.

c.OpenAI GPT:
Generates intelligent, context-driven responses based on customer input and conversation history.

d.Concurrency:
Uses Python's ThreadPoolExecutor to manage multiple simultaneous calls efficiently.

e.Workflow:
Calls are initiated via the /bulk_call endpoint.
Customer speech is processed in real-time at the /voice endpoint.
The AI crafts responses and ensures a natural flow of conversation.

4. Notes
Ensure proper configuration of Twilio and OpenAI credentials.
Use ngrok to expose your local server for Twilio callbacks during development.
This project is designed to be scalable and efficient, making it ideal for handling high call volumes in sales campaigns.

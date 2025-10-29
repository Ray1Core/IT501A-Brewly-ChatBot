👽 IT501A – AlienBot (Brewly Chat Bot)
AlienBot is a web-based chatbot designed for students, baristas, and coffee lovers.
It provides interactive recipe assistance for drinks such as frappes, milkshakes, smoothies, and lattes — powered by OpenAI’s API via a secure proxy endpoint.

🧠 Overview
AlienBot acts as a coffee shop recipe expert that users can chat with.
It uses HTML, CSS, and JavaScript to create a responsive chat interface and handles AI responses dynamically.

The chatbot interacts with a proxy-based OpenAI endpoint (https://alcuino-chatbot.azurewebsites.net/api/OpenAIProxy) to ensure that the actual API key remains hidden from users.

⚙️ Main Features
💬 Real-time chat with a coffee recipe expert (AI-powered)
🌗 Light/Dark mode switch (stored in localStorage)
⚡ Responsive layout using Bootstrap 5
🧾 Dedicated Settings page with:
Theme toggle
Version and model info
“Clear Chat” feature
🧠 Uses OpenAI GPT model for generating recipes
🔒 Secure configuration (API key excluded via .gitignore)
🧩 Folder & File Structure
Chatbot/
├── index.html        # User interface layout and HTML structure
├── style.css         # Design, color themes, and UI styling
├── script.js         # Chat logic and API handling
├── config.js         # API key storage (local use only)
└── .gitignore        # Protects sensitive files from upload

🖥️ Interface Overview
1. Sidebar
Displays menu items: Chat and Settings
Includes Dark Mode toggle switch
Shows user profile area at the bottom
2. Main Chat Area
Displays conversation between the user and AlienBot
Automatically scrolls to the latest message
Uses dynamic message elements (<div class="message user/bot">)
3. Settings Page
Toggle for appearance (Dark/Light)
Shows app version, model used, and “Clear Chat” button
💻 Code Documentation
1. Configuration (config.js)
let _config = {
  openAI_api: "https://alcuino-chatbot.azurewebsites.net/api/OpenAIProxy",
  openAI_model: "gpt-4o-mini",
  ai_instruction: "You are a friendly coffee shop barista expert...",
  response_id: "",
  api_key: window.OPENAI_KEY || ""
};

Properties
Property	Type	Description
openAI_api	string	The proxy endpoint that forwards requests to OpenAI.
openAI_model	string	Specifies the model version used (e.g., gpt-4o-mini).
ai_instruction	string	The system prompt that defines the chatbot’s tone and behavior.
response_id	string	Keeps track of the current conversation session.
api_key	string	The local API key used for authentication (hidden via .gitignore).
2. Core Methods
addUserMessage(text)
Purpose: Displays the user’s input in the chat body.
Parameters: text (string) — the user’s typed message.
Usage Example:
addUserMessage("Show me how to make a caramel macchiato");

addBotMessage(htmlContent)
Purpose: Renders the AI’s response as a styled message bubble.
Parameters: htmlContent (string) — formatted text returned by OpenAI.
Usage Example:
addBotMessage("Sure! Here’s how to make it...");

sendOpenAIRequest(text)
Purpose: Handles communication with the OpenAI proxy API.
Parameters: text (string) — message from the user.
Returns: AI-generated text response.
Usage Example:
await sendOpenAIRequest("How to make a mocha latte?");

sendMessage()
Purpose: The main message flow — captures user input, sends it to OpenAI, and displays both sides of the conversation.
Usage: Triggered when pressing Enter or clicking the Send button.
setDarkMode(enabled)
Purpose: Switches between dark and light themes.
Parameters: enabled (boolean) — true for dark mode, false for light mode.
Usage Example:
setDarkMode(true);

🧰 Usage Flow

User Input
The user types a message in the input box and presses Enter.

Display User Message
The message appears in the chat window using addUserMessage().

Send Request
sendOpenAIRequest() formats and sends the input to the proxy API.

Receive AI Response
The API sends back a message, which is displayed using addBotMessage().

Persistent Theme
setDarkMode() ensures the user’s theme choice is saved via localStorage.

🧾 .gitignore
Ensures sensitive files and dependencies aren’t uploaded:
config.js
node_modules/
🚀 Setup Instructions
Clone the Repository
git clone https://github.com/Ray1Core/IT501A-Brewly-ChatBot.git

Add Your API Key
Create a file named config.js inside the Chatbot/ folder:
window.OPENAI_KEY = "your-actual-OpenAI-API-key";

Run Locally
Open index.html directly in your browser — no server setup needed.

☕ Credits
Developed by Ray1Core
For IT501A Project – Interactive Coffee Chatbot
Powered by OpenAI GPT-4o-mini through a secure proxy.
“Brewing creativity, one chat at a time.” 👽☕

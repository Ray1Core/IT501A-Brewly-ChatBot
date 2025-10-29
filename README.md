👽 IT501A – AlienBot (Brewly Chat Bot)
AlienBot is a web-based chatbot designed for students, baristas, and coffee lovers.
It provides interactive recipe assistance for drinks such as frappes, milkshakes, smoothies, and lattes — powered by OpenAI’s API via a secure proxy endpoint.

🧠 Overview
AlienBot acts as a coffee shop recipe expert that users can chat with.
It uses HTML, CSS, and JavaScript to create a responsive chat interface and handles AI responses dynamically through the OpenAI API proxy.

⚙️ Main Features
💬 Real-time AI chat for drink recipes and brewing techniques
🌗 Light/Dark mode switch with persistent storage
🧾 Settings page with app info and chat clearing
📱 Responsive Bootstrap 5 layout
🔒 Secure configuration (API key excluded via .gitignore)
🧩 Folder Structure
Chatbot/
├── index.html       # Main layout and UI
├── style.css        # Visual styling and color themes
├── script.js        # Core chatbot logic
├── config.js        # Local API key (ignored by Git)
└── .gitignore       # Protects sensitive files

⚙️ Properties (from _config)
Property                     	Type	                 Description
openAI_api	                string                  	Proxy endpoint for OpenAI API (secured)
openAI_model	              string                  	Model used (e.g. gpt-4o-mini)
ai_instruction	            string	                  System instruction defining the bot’s tone and topic
response_id	string	        Tracks                    conversation history
api_key	string	            API key                   (local only; excluded from repo)

🧠 Methods (Core Functions)
addBotMessage(htmlContent)
Appends an AI-generated message to the chat area using styled HTML.
addUserMessage(text)
Displays the user’s input in the chat body with custom bubble styling.
sendOpenAIRequest(text)
Sends the user input to the OpenAI API proxy and retrieves the AI response.
sendMessage()

Main controller that:
Gets the user input
Displays it
Calls sendOpenAIRequest()
Displays the AI response
setDarkMode(enabled)

Toggles dark/light themes and stores preference in localStorage.
clearChatBtn (Event)
Resets the chat interface and restarts with the greeting message.

🧩 Usage Flow
User opens index.html
Chat interface loads with greeting message
User types a question (e.g., “How do I make a caramel frappe?”)
Bot replies with:
Ingredients list
Step-by-step brewing instructions
Optional serving tips
💻 Setup & Installation
Clone the repository
git clone https://github.com/Ray1Core/IT501A-Brewly-ChatBot.git

Create config.js
window.OPENAI_KEY = "your-actual-key-here";

Run locally
Just open index.html in a browser — no server setup required.
🎨 Interface Overview
Sidebar
Chat / Settings menu
Dark Mode switch
User profile section
Chat Window
Dynamic message bubbles
Scrollable chat body
Input and send button
Settings
Toggle dark mode
Clear chat button
App version and model info
🧾 .gitignore
config.js
node_modules/

☕ Credits
Developed by Ray1Core
For IT501A Project – Interactive Coffee Chatbot
Powered by OpenAI GPT-4o-mini via secure proxy.

“Brewing creativity, one chat at a time.” 👽☕
📚 Appendix – About Markdown
Markdown was introduced in 2004 to simplify HTML for documentation.
Its widespread adoption came after GitHub (2008) made .md the default format for project READMEs.
Today, Markdown powers documentation for almost all open-source projects.

# 🌱 KrishiSakhi — AI Assistant for Farmers

**KrishiSakhi** is a multilingual AI-powered farming assistant designed to help farmers get instant guidance about crops, pests, irrigation, weather, and government schemes.

The system provides a **chat interface supporting text, voice, and images**, allowing farmers to ask questions in **English or Malayalam** and receive AI-powered responses.

🔗 **Live Demo**  
https://68d629c367bc6913a4355220--gorgeous-crumble-640517.netlify.app/

---

# Problem Statement

Agriculture remains the primary livelihood for millions of farmers, yet many farmers face challenges such as:

- Lack of timely agricultural guidance  
- Difficulty diagnosing crop diseases  
- Limited access to expert consultation  
- Language barriers in digital tools  

Traditional agricultural advisory systems often require **manual visits or complex applications**. Many farmers need a **simple conversational interface that works directly from a phone**.

KrishiSakhi addresses this problem by providing a **conversational AI assistant that farmers can interact with using text, voice, or images.**

---

# Solution Overview

KrishiSakhi provides a **web-based conversational interface** that connects farmers with an AI-powered backend through an automation workflow.

The assistant can:

- Answer farming-related questions  
- Analyze crop images  
- Accept voice queries  
- Respond in the local language  
- Provide contextual agricultural guidance  

The system integrates **frontend UI, speech capture, camera input, and a backend automation workflow (n8n)** to deliver real-time responses.

---

# Key Features

## Multilingual Support

Supports communication in:

- English  
- Malayalam  

Farmers can **toggle language directly from the interface**.

---

## Voice Interaction

Farmers can:

- Hold the microphone button  
- Speak their question  
- Send voice queries to the AI assistant  

Voice recording is converted to **MP3 format** and sent to the backend for processing.

---

## Image-based Queries

Farmers can capture or upload images of:

- Crop diseases  
- Pest infestations  
- Plant damage  

Images are sent to the backend where they can be processed by AI models for diagnosis.

---

## Chat-based AI Interaction

The chatbot allows users to ask questions such as:

- Crop management techniques  
- Irrigation advice  
- Pest control solutions  
- Weather-related farming decisions  
- Government agricultural schemes  

---

## Mobile-Friendly Interface

The UI is optimized for **mobile farmers** with:

- Simple conversational design  
- Camera access  
- Voice recording  
- Low cognitive complexity  

---

# System Architecture

The application follows a lightweight **frontend → webhook → AI backend architecture**.

Farmer (Mobile / Browser)
│
│ Text / Voice / Image
▼
Frontend Chat Interface
│
│ HTTP POST Request
▼
n8n Webhook Endpoint
│
│ AI Processing
▼
AI Response
│
▼
Frontend Chat UI


---

# Technologies Used

## Frontend

- HTML5  
- TailwindCSS  
- JavaScript  
- Lucide Icons  

---

## Media Processing

- Web Audio API (voice recording)  
- LameJS (MP3 encoding)  
- WebRTC / MediaDevices API (camera capture)  

---

## Backend Integration

- n8n Automation Platform  
- Webhook API communication  
- AI response processing  

---

# Core Functionalities Implemented

## Chat Messaging

Users can send messages through:

- Text input  
- Voice recording  
- Image capture  

Messages are transmitted to the backend using an HTTP POST request:

```javascript
fetch(webhookUrl, {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    type,
    message,
    lang,
    userId
  })
})

Voice Processing

Voice input workflow:

User holds microphone button

Browser records audio via MediaRecorder

Audio converted to MP3 using LameJS

Encoded audio sent to backend

Backend processes speech and returns response

Camera Integration

Farmers can capture crop images using the device camera.

The system:

Accesses camera via getUserMedia

Captures image frame using <canvas>

Converts image to Base64

Sends the image to backend

Real-Time Response Handling

The backend may return:

JSON text responses

Audio responses

If the response contains audio:

const audio = new Audio(url);
audio.play();

The assistant plays the audio reply automatically.

User Interface Design

The UI was designed with farmers in mind:

Dark mode reduces eye strain

Large interaction buttons

Minimal navigation complexity

Mobile-first layout

Components include:

Header with language toggle

Chat message area

Input composer

Voice button

Camera modal

Project Structure
KrishiSakhi
│
├── KrishiSakhiBot.html   # Main chatbot interface
├── README.md             # Project documentation
How to Run the Project

Clone the repository:

git clone https://github.com/krishnahanda484/KrishiSakhi.git

Navigate into the project directory:

cd KrishiSakhi

Open the HTML file in a browser:

open KrishiSakhiBot.html

Or deploy using:

Netlify

Vercel

GitHub Pages

Live Deployment

The application is deployed using modern static hosting platforms.

Production link

https://68d629c367bc6913a4355220--gorgeous-crumble-640517.netlify.app/

Potential Improvements

Future versions of KrishiSakhi could include:

AI crop disease classification models

Integration with weather APIs

Government scheme recommendation system

Offline-first functionality for rural areas

Farmer profile personalization

SMS / WhatsApp integration

Impact

KrishiSakhi demonstrates how AI-powered conversational interfaces can improve accessibility to agricultural knowledge for rural communities.

The project showcases:

Human-centered AI design

Multimodal input handling (text, voice, image)

AI workflow automation

Web-based deployment

Author

Krishna Handa

Computer Science Engineering Student
AI Automation Developer

GitHub
https://github.com/krishnahanda484

License

This project is open source and available under the MIT License.


---

Small GitHub trick that separates beginner repos from professional ones: place **this section at the very top** of the README:

```markdown
 ⭐ Star this repository if you find it useful!

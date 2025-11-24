Jarvis: A Voice-Controlled Personal Assistant

Introduction

Jarvis is a modern, voice-activated virtual assistant built in Python. Designed to handle general tasks similar to commercial products like Alexa and Google Assistant, Jarvis uses state-of-the-art libraries for speech recognition, text-to-speech, and generative AI to provide a responsive and conversational user experience.

The core goal of this project is to create an open-source, extensible, and locally runnable assistant that can interface with the web and external services.

Core Features

Voice Activation: Listens for the wake word "Jarvis" to begin processing commands.

Speech-to-Text (STT): Uses Google's Speech Recognition API to convert spoken commands into text.

Text-to-Speech (TTS): Generates high-quality speech output using Google Text-to-Speech (gTTS) and plays audio using pygame.

Generative AI Integration: Uses the OpenAI API (gpt-3.5-turbo) for complex, conversational queries.

Web Integration: Can open popular websites (Google, YouTube, Facebook, LinkedIn).

Music Playback: Play songs by name from a local music library using webbrowser.

News Headlines: Fetches and reads top news headlines from the NewsAPI (currently configured for India).

Prerequisites

To run Jarvis, you need Python 3.x and the following libraries. It is highly recommended to use a virtual environment.

Required Python Libraries

You can install all necessary packages using pip:

pip install SpeechRecognition pyttsx3 gTTS pygame requests openai


(Note: The project currently uses gTTS and pygame for speaking, overriding the initial pyttsx3 implementation.)

API Keys

This project requires two external API keys for full functionality:

OpenAI API Key: For the AI-powered conversation capabilities.

Set the key within the aiProcess function in main.py.

NewsAPI Key: For fetching current news headlines.

Set the key in the newsapi variable near the top of main.py.

Installation and Setup

1. Clone the repository (or set up the files)

Ensure main.py, client.py, and musicLibrary.py are in the same directory.

2. Configure API Keys

Replace the placeholder <Your Key Here> in both main.py and client.py with your actual API keys.

3. Configure Music Library

Edit musicLibrary.py to customize the songs Jarvis can play. The current structure is:

music = {
    "stealth": "[https://www.youtube.com/watch?v=](https://www.youtube.com/watch?v=)...",
    "march": "[https://www.youtube.com/watch?v=](https://www.youtube.com/watch?v=)...",
    # Add your own key-value pairs here
}


The key is the song name you say, and the value is the direct link (e.g., YouTube URL).

Usage

To start the assistant, run the main.py file from your terminal:

python main.py


Wait for Initialization: Jarvis will announce, "Initializing Jarvis...."

Activate: Wait for the assistant to enter the "Listening..." state.

Say the Wake Word: Say "Jarvis".

Confirm: Jarvis will respond with "Ya".

Give a Command: Immediately after the confirmation, give your command.

Example Commands

Command

Action

Jarvis, open youtube

Opens YouTube in your default web browser.

Jarvis, play march

Opens the YouTube link associated with "march" in musicLibrary.py.

Jarvis, what is the capital of France?

Sends the query to the OpenAI model and reads the response.

Jarvis, read the news

Fetches and speaks the top headlines.

Development Notes

The project uses gTTS and pygame for a robust, cross-platform Text-to-Speech solution, dynamically generating and playing a temp.mp3 file. This approach is more reliable than the initial pyttsx3 implementation for speech generation.# Jarvis
An AI Agent that works on voice of yours.

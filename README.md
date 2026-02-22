Voice-Activated System Controller
A Python-based utility that monitors audio input in real-time to execute system commands via voice. Currently configured to handle secure, hands-free system shutdowns using the Google Speech Recognition API.

🚀 Features
Real-time Audio Processing: Continuous background monitoring with dynamic energy thresholding to adapt to ambient noise.

Cross-Platform Logic: Built with a modular structure to detect and handle different Operating Systems (Windows support included).

Graceful Termination: Includes a safety buffer (5-second delay) before execution to prevent accidental shutdowns.

Robust Error Handling: Managed exceptions for network timeouts, unintelligible speech, and user interrupts.

🛠️ Prerequisites
Before running the script, ensure you have the following installed:

Python 3.7+

PyAudio: Required for microphone access.

Windows: pip install pyaudio

Linux: sudo apt-get install python3-pyaudio

SpeechRecognition Library:

pip install SpeechRecognition

📦 Installation & Setup
Clone the Repository:

Bash

git clone https://github.com/Eamon2009/Shutdown_by_voice.git
cd voice-system-control
Install Dependencies:

Bash

pip install -r requirements.txt
Run the Monitor:

Bash

python voice_monitor.py
🖥️ Usage
Once the script is active, it will display --- Voice Control Active ---.

Trigger Command: Clearly say "Shutdown system".

Execution: The script will log the detection and trigger a 5-second countdown before the OS executes the power-off sequence.

Exit: Press Ctrl + C in the terminal to stop the monitor manually.

⚙️ How it Works
The script utilizes a continuous while loop combined with the recognizer.listen() method.

Component	Function
dynamic_energy_threshold	Automatically adjusts to the room's noise level for better accuracy.
recognize_google	Sends audio snippets to Google’s Web Speech API for high-accuracy transcription.
os.system	Interfaces directly with the Windows shell to execute the /s (shutdown) command.

Export to Sheets

⚠️ Safety Note
This script executes a forced shutdown. Ensure all work is saved before testing the voice command. To cancel a pending shutdown on Windows after the script has run, you can quickly type shutdown /a in a command prompt.

🤝 Contributing
Contributions are welcome! If you would like to add support for macOS/Linux commands or additional voice triggers (like "Restart" or "Sleep"), please feel free to fork the repo and submit a pull request.

Disclaimer: This tool is intended for personal automation and accessibility purposes. Use with caution in production environments.

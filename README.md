# FirebaseRTC

A real-time video chat application built with WebRTC and Firebase Cloud Firestore for signaling.

## Overview

FirebaseRTC demonstrates how to build a video calling application using WebRTC with Firebase Cloud Firestore as the signaling server. This application allows users to create or join video chat rooms and communicate in real-time with audio and video.

## Features

- Real-time video and audio communication
- Create new video chat rooms
- Join existing rooms via room ID
- Uses Firebase Cloud Firestore for WebRTC signaling
- Implements STUN servers for NAT traversal
- Simple and intuitive UI with Material Design components

## Prerequisites

- Firebase account
- A modern web browser that supports WebRTC (Chrome, Firefox, Safari, Edge)
- Node.js and npm (for local development)

## Setup and Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/FirebaseRTC.git
   cd FirebaseRTC
   ```

2. Create a Firebase project at [https://console.firebase.google.com/](https://console.firebase.google.com/)

3. Enable Cloud Firestore in your Firebase project

4. Update the Firebase configuration in the project (if needed)

5. Deploy to Firebase:
   ```
   firebase deploy
   ```

   Or run locally:
   ```
   firebase serve
   ```

## Usage

1. Open the application in your browser
2. Click "Open camera & microphone" to grant media permissions
3. To start a new call:
   - Click "Create room"
   - Share the displayed room ID with the person you want to call
4. To join an existing call:
   - Click "Join room"
   - Enter the room ID shared with you
   - Click "Join"
5. To end the call, click "Hangup"

## Project Structure

- `public/` - Contains all the frontend code
  - `index.html` - Main HTML file
  - `app.js` - Application logic and WebRTC implementation
  - `main.css` - Styling for the application
- `firebase.json` - Firebase configuration file
- `database.rules.json` - Firebase database rules

## How It Works

The application uses WebRTC for peer-to-peer communication and Firebase Cloud Firestore for signaling:

1. When a user creates a room, the app generates an offer using WebRTC
2. The offer is stored in Firebase Cloud Firestore
3. When another user joins with the room ID, they retrieve the offer from Firestore
4. The joining user creates an answer and stores it in Firestore
5. Both peers exchange ICE candidates through Firestore
6. A peer-to-peer connection is established for video/audio streaming

## Technologies Used

- WebRTC API
- Firebase Cloud Firestore
- Material Design Components
- JavaScript (ES6+)

## License

This project is based on the Firebase WebRTC codelab and is available under the MIT License.

## Resources

- [WebRTC.org](https://webrtc.org/)
- [Firebase Documentation](https://firebase.google.com/docs)
- [WebRTC Samples](https://webrtc.github.io/samples/)

## Troubleshooting

- Ensure your browser supports WebRTC
- Check that camera and microphone permissions are granted
- For connection issues, verify that you're not behind a restrictive firewall
- Make sure Firebase configuration is correct
# Lets-Call
#Video-Calling-website (real time communication)
# peer to peer WebRTC application

Lets call is a real time video calling website which enables two users to connect on video call.
features: video call, audio call, 
technologies used are html, css, javaScript, WebRTC agora

installation:
1: Create an account on agora.io and create an app to generate an APP ID
2: Update APP ID, Temp Token and Channel Name in main.js

working: open the website in two seperate tabs & enable camera on site-setting.

link : https://nitin014.github.io/Lets-Call/

Explaination of the whole js code:
This code is for a simple video conferencing application using WebRTC and Agora RTM (Real-Time Messaging) SDK. Let's break down the main components and their functionality:

1. **Initialization and Setup**:
   - `APP_ID` is a unique identifier for the application.
   - `uid` is a randomly generated user ID.
   - `roomId` is retrieved from the URL parameters. If not present, the user is redirected to the lobby page.
   - Constraints for local video and audio streams are defined.

2. **Initialization Function `init`**:
   - Creates an instance of the Agora RTM client and logs in with the generated `uid`.
   - Creates a channel with the provided `roomId` and joins it.
   - Sets up event listeners for user joining, leaving, and receiving messages.
   - Retrieves the local media stream using `getUserMedia` and displays it on the page.

3. **Event Handlers**:
   - `handleUserLeft`: Removes the remote user's video stream and adjusts the UI.
   - `handleMessageFromPeer`: Processes messages received from peers, such as offers, answers, and ICE candidates.
   - `handleUserJoined`: Triggered when a new user joins the channel, initiates the offer creation process.

4. **Peer Connection Management**:
   - `createPeerConnection`: Initializes a new RTCPeerConnection with ICE servers and sets up event handlers for track and ICE candidate events.
   - `createOffer`: Initiates the offer creation process for establishing a connection with the remote peer.
   - `createAnswer`: Responds to an offer from a remote peer by creating an answer and exchanging SDP descriptions.
   - `addAnswer`: Adds the received answer from the remote peer.

5. **UI Interaction**:
   - `toggleCamera` and `toggleMic` functions toggle the local video and audio streams, respectively, on and off.
   - Event listeners are set up for toggling camera and mic buttons.

6. **Cleanup**:
   - `leaveChannel` function is called before unloading the window to gracefully exit the channel and log out from the Agora RTM client.

Overall, this code sets up a basic video conferencing application where users can join a room, see each other's video streams, toggle their own camera and mic, and leave the room gracefully. It utilizes WebRTC for real-time communication and Agora RTM for messaging between peers.

### Deepfake Detector Browser Extension

#### Introduction
The Deepfake Detector Extension is a browser extension designed to help users identify deepfake videos in real-time. It uses a machine learning-based backend to analyze frames of the video content and provides an authenticity score, giving users insight into the trustworthiness of the video content they are watching.

#### Features
- **Real-Time Analysis**: Analyzes frames of videos on the fly while they are being played in the browser.
- **Authenticity Score**: Provides an authenticity score and alerts users if a video might be a deepfake.
- **Manual Video Analysis**: Users can manually analyze the current video via the popup interface.
- **Background Listener**: Listens for video content loading and starts analysis automatically.

#### Usage Instructions
1. **Setup Dependencies**: Install necessary Python packages using `pip` to set up the backend server for analysis.
   - The backend server for deepfake analysis should be implemented separately (e.g., Flask-based server running an ML model).

2. **Run Backend Server**: Ensure that the backend server is running locally on `http://localhost:5000/analyze`.

3. **Install Extension**:
   - Open your Chrome browser and navigate to `chrome://extensions/`.
   - Enable **Developer mode**.
   - Click **Load unpacked** and select the folder containing the extension files (including `manifest.json`).

4. **Using the Extension**:
   - When watching a video, the extension will automatically analyze and display the authenticity score in a small overlay.
   - Alternatively, open the extension popup and click **Analyze Current Video** to manually trigger an analysis.

#### Prerequisites
- **Chrome Browser**: The extension is developed for Google Chrome.
- **Backend Server**: The backend deepfake analysis must be implemented and running to receive the analysis data.

#### How It Works
1. **Content Script**: Injects a script into each page to listen for HTML video elements and analyze frames.
2. **Video Analysis**: Extracts frames from video content using an HTML canvas and sends them to the backend server.
3. **Scoring and Alerts**: Receives an authenticity score from the backend and displays it in real-time.
4. **Popup Action**: The extension's popup allows for manual analysis by the user.

#### Disclaimer
This extension is for educational purposes only. Users are responsible for ensuring that they have permission to analyze content and comply with all applicable laws.

#### License
This project is open-source and licensed under the MIT License.

---

**Note**: The machine learning model for deepfake detection must be implemented separately and integrated into the backend server. This browser extension sends frames to the backend for analysis and displays the results to the user.

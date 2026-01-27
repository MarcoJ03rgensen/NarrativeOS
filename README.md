# Narrative - Creative Writing Platform

A distraction-free, browser-based creative writing environment with AI assistance and Firebase Cloud sync.

## Features
- **Distraction-Free Editor**: Clean interface focused on writing.
- **AI Creative Assistant**: Integrated Google Gemini AI to help expand scenes, describe atmosphere, or overcome writer's block. This is a free site with no adds - you need your own api-key
- **Cloud Sync**: Keep your work safe and accessible across devices using Google Firebase (Firestore).
- **World Bible**: Track characters, locations, and lore.
- **Analysis Tools**: Pacing alerts, "Show, Don't Tell" detection, and rhythm analysis.

## How to Enable Cloud Sync (Firebase)

Narrative uses Google Firebase for real-time cloud storage. You need to create a free Firebase project.

1. **Go to Firebase Console**
   Visit [https://console.firebase.google.com/](https://console.firebase.google.com/).

2. **Create a Project**
   - Click "Add project" and follow the steps.
   - Disable Google Analytics if you want a simpler setup.

3. **Enable Firestore Database**
   - In your project dashboard, go to **Build > Firestore Database**.
   - Click **Create Database**.
   - Select a location (e.g., `nam5` or `eur3`).
   - Start in **Test Mode** (or configure rules strictly later).

4. **Enable Authentication**
   - Go to **Build > Authentication**.
   - Click **Get Started**.
   - Select **Google** from the providers list and enable it.
   - Save.

5. **Get Configuration**
   - Click the **Gear icon** (Project Settings) near the top left.
   - Scroll down to "Your apps".
   - Click the **Web icon** (`</>`) to add a web app.
   - Register the app (you don't need Firebase Hosting).
   - You will see a `firebaseConfig` object code block.

6. **Connect Narrative**
   - Copy the content inside the `firebaseConfig` variable (the part starting with `{ apiKey: ... }`).
   - Open Narrative.
   - Click the **Cloud Icon** in the sidebar.
   - Paste the configuration JSON into the box.
   - Click "Save Configuration" and then "Sign in with Google".

## How to Enable AI Features (Free)

Narrative uses Google's Gemini API, which offers a generous free tier. You need your own API key to use the AI features.

1. **Go to Google AI Studio**
   Visit [https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey).

2. **Sign In**
   Log in with your Google account.

3. **Create an API Key**
   - Click on the **"Create API key"** button.
   - Select **"Create API key in new project"**. This is the simplest option and handles the cloud project setup for you automatically without needing to manually configure a Google Cloud Console project.
   - Alternatively, if you have existing Google Cloud projects, you can select "Create API key in existing project".

4. **Copy the Key**
   - Copy the generated string (it starts with `AIza...`).

5. **Activate in Narrative**
   - Open Narrative.
   - Click the **AI Icon** (Lightning bolt) in the bottom right corner.
   - In the input field at the bottom of the panel, paste your API key when prompted.
   - The key is saved locally in your browser, so you only need to do this once.

## Using Open Source Models (Hugging Face)

You can also use open-source models like Bloom or Llama via Hugging Face.

1. Get a token from [Hugging Face Settings](https://huggingface.co/settings/tokens).
2. Select "Hugging Face" in the AI provider dropdown.
3. Enter your token.

**Note on CORS Errors:**
Because this runs entirely in the browser (client-side), you may encounter "CORS" or "Failed to fetch" errors when connecting to Hugging Face. This is a browser security feature.
*   **Workaround (For personal use only):** You can try to install a "Allow CORS" extension in your browser to bypass this restriction while you work. Note that this is a developer hack and only works for your specific browser instance. Turn it ON when working on your story. Turn it OFF when browsing the normal web (for security). This may not work.

## Using GitHub Models (Azure AI)

You can use models like GPT-4o, Llama 3.1, and Phi-3 via GitHub Models.

1.  **Get a Token**: Go to [GitHub Settings > Developer Settings > Personal Access Tokens (Classic)](https://github.com/settings/tokens).
2.  Generate a new token (no specific scopes are needed for public models, but `read:user` is safe).
3.  Select "GitHub Models" in the AI provider dropdown.
4.  Enter your token.

**Note:** GitHub Models (via Azure AI) may also have CORS restrictions similar to Hugging Face when accessed directly from a browser.

## GitHub Gist Integration (Legacy)

*Note: This feature has been superseded by the Firebase Cloud Sync integration. It is recommended to migrate your workflow to Firebase as described above.*

To enable legacy cloud sync (read-only mode for old projects), the application uses GitHub Gists to store your projects as JSON files.

1.  **Get a Token**: Go to [GitHub Settings > Developer Settings > Personal Access Tokens (Classic)](https://github.com/settings/tokens).
2.  Generate a new token with the **`gist`** scope.
3.  In Narrative, click "Connect" in the cloud menu and enter your token.
4.  Your data will be stored in a private Gist named "NarrativeOS Data".

## License

**Copyright (c) 2025 Marco Birkedahl Jørgensen. All Rights Reserved.**

This project is proprietary software. Unauthorized copying, modification, distribution, or use of this file, except via the public site, is strictly prohibited. The software is provided "as is" without warranty of any kind.
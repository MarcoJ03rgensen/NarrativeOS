# NarrativeOS

A distraction-free, browser-based creative writing environment with AI assistance and Google Drive sync.

## Features
- **Distraction-Free Editor**: Clean interface focused on writing.
- **AI Creative Assistant**: Integrated Google Gemini AI to help expand scenes, describe atmosphere, or overcome writer's block. This is a free site with no adds - you need your own api-key
- **Google Drive Sync**: Keep your work safe and accessible across devices.
- **World Bible**: Track characters, locations, and lore.
- **Analysis Tools**: Pacing alerts, "Show, Don't Tell" detection, and rhythm analysis.

## How to Enable AI Features (Free)

NarrativeOS uses Google's Gemini API, which offers a generous free tier. You need your own API key to use the AI features.

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

5. **Activate in NarrativeOS**
   - Open NarrativeOS.
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

## Google Drive Integration

To enable cloud sync, the application uses a default configuration. If you are hosting this yourself, you may need to configure your own Google Cloud Project credentials in the code.
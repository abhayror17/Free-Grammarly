# Gemini AI Corrector Chrome Extension

A Chrome extension that automatically corrects and enhances your writing on any website using Google's Gemini AI. This extension works like Grammarly, providing real-time spelling, grammar, and clarity improvements as you type.

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/2c84d7e3c5c546d6b442286993d0c668" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
## Features

- 🚀 **Automatic Text Enhancement**: Fixes spelling and grammar mistakes while improving clarity and tone
- 🌐 **Works on Any Website**: Supports all text inputs, textareas, and content-editable elements
- ⚡ **Real-time Processing**: Auto-triggers after you stop typing (1.2-second delay) or when you leave a text field
- 🎛️ **Easy On/Off Toggle**: Enable or disable the extension with a simple button in the popup
- 🔐 **Secure API Key Storage**: Your Gemini API key is stored securely in Chrome's sync storage
- 📝 **Smart Text Detection**: Only processes text fields with at least 10 characters
- 🎨 **Visual Feedback**: Color-coded borders show processing status (orange = processing, green = success, red = error)

## Installation

### Prerequisites
- Google Chrome browser
- A Google Gemini API key (get one from [Google AI Studio](https://makersuite.google.com/app/apikey))

### Steps
1. **Download the Extension**
   - Clone or download this repository to your local machine

2. **Load into Chrome**
   - Open Chrome and navigate to `chrome://extensions/`
   - Enable "Developer mode" in the top-right corner
   - Click "Load unpacked" and select the extension folder

3. **Configure API Key**
   - Click the extension icon in Chrome's toolbar
   - Enter your Gemini API key in the popup
   - Click "Save Key"

## Usage

### Basic Usage
1. **Enable the Extension**: Click the extension icon and ensure it shows "ACTIVE"
2. **Start Typing**: Type in any text field on any website
3. **Automatic Enhancement**: After you stop typing for 1.2 seconds or leave the field, your text will be automatically enhanced

### Managing the Extension
- **Enable/Disable**: Click the extension icon and use the toggle button
- **Change API Key**: Enter a new key in the popup and click "Save Key"
- **Status Indicators**:
  - Orange border: Text is being processed
  - Green border: Enhancement successful
  - Red border: Error occurred

### Supported Text Fields
- Standard input fields (text, email, search, URL)
- Textareas
- Content-editable elements
- Most rich text editors

## File Structure

```
gemini-auto-enhancer/
├── manifest.json      # Extension configuration and permissions
├── background.js      # Service worker handling API calls
├── content.js        # Script injected into web pages
├── popup.html        # Extension popup interface
├── popup.js          # Popup functionality and settings
└── README.md         # This file
```

## Technical Details

### Architecture
- **Manifest V3**: Uses the latest Chrome extension manifest version
- **Service Worker**: Background script handles Gemini API communication
- **Content Script**: Monitors and enhances text fields on web pages
- **Popup Interface**: Provides settings and control interface

### API Integration
- Uses Google's Gemini 2.0 Flash model via the REST API
- Endpoint: `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent`
- Secure header-based authentication with API key

### Performance Optimizations
- Debounced input handling (1.2-second delay)
- Minimum text length requirement (10 characters)
- Prevents multiple simultaneous enhancements on the same element
- Automatic cleanup of visual indicators

## Permissions

The extension requires minimal permissions:
- `storage`: To save your API key and extension settings
- `host_permissions` for `https://generativelanguage.googleapis.com/`: To communicate with the Gemini API

## Privacy & Security

- Your API key is stored locally in Chrome's sync storage
- Text is only sent to Google's Gemini API for processing
- No data is collected or stored by the extension
- All communication uses HTTPS encryption

## Troubleshooting

### Common Issues

**"API Key not found" Error**
- Solution: Click the extension icon and enter your Gemini API key

**Red border appears (API Error)**
- Check if your API key is valid
- Ensure you have API quota remaining
- Verify your internet connection

**Extension not working**
- Check if the extension is enabled in the popup
- Ensure the text field has at least 10 characters
- Try refreshing the webpage

**Text not being enhanced**
- Wait for the 1.2-second delay after typing
- Try clicking outside the text field to trigger enhancement
- Check if the extension is enabled

### Getting Help
If you encounter issues:
1. Check the browser console for error messages
2. Verify your API key is correctly entered
3. Ensure you have sufficient API quota
4. Try disabling and re-enabling the extension

## Development

### Local Development
1. Clone the repository
2. Make your changes
3. Load the unpacked extension in Chrome
4. Test on various websites

### Contributing
Feel free to submit issues and enhancement requests!

## Version History

- **v5.0**: Current version with on/off toggle functionality
- Enhanced error handling and user feedback
- Support for all major text input types

## License

This project is open source. Feel free to modify and distribute according to your needs.

---
<img width="469" height="401" alt="image" src="https://github.com/user-attachments/assets/c6b5f1b2-bec9-4fdb-9ac9-41017b7e0d9f" />


**Note**: This extension requires a valid Google Gemini API key to function. Make sure to keep your API key secure and monitor your usage to avoid unexpected charges.

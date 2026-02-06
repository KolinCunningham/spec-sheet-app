# SpecSheet - Annotated Instruction Sheets

A web application optimized for iPad that allows users to create annotated printable sheets for instructions or specifications.

## Features

### 1. Photo Capture and Arrangement
- Take photos using device camera or upload existing images
- Photos auto-arrange on a landscape-oriented paper (A4/Letter/Legal)
- Drag and resize photos on the canvas
- Multiple photos supported per sheet

### 2. Annotation Tools
- **Arrow** - Draw directional arrows with arrowheads
- **Circle** - Create circular markers/highlights
- **Line** - Draw straight lines
- **Rectangle** - Draw rectangular boundaries
- **Text** - Add text labels with customizable font size
- **Freehand** - Draw freely with stylus or finger
- Customizable colors (10 preset colors)
- Adjustable stroke width (1-10px)

### 3. Voice Memo Integration
- Record voice memos describing instructions
- Real-time speech-to-text transcription (Web Speech API)
- Convert transcriptions directly to text annotations
- Works on supported browsers (Chrome, Safari, Edge)

### 4. AI-Generated Suggestions
- Integrates with OpenAI GPT API
- Analyzes your annotations and photos
- Suggests improvements for clarity and professionalism
- One-click to add suggestions as annotations

### 5. PDF Export
- Export as landscape-oriented PDF
- Configurable quality (72/150/300 DPI)
- Automatic filename with title and date
- Professional header with title, creator, and date

### 6. Offline Support
- Service worker caches app for offline use
- Camera and basic editing work offline
- AI features require internet connection

## Deployment

### Option 1: Local Testing
Simply open `index.html` in a modern browser. Note that camera access requires HTTPS or localhost.

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

### Option 2: Deploy to GitHub Pages
1. Create a new GitHub repository
2. Upload `index.html` and `sw.js`
3. Go to Settings > Pages
4. Select main branch and save
5. Access at `https://yourusername.github.io/repo-name`

### Option 3: Deploy to Netlify
1. Drag and drop the folder to [Netlify Drop](https://app.netlify.com/drop)
2. Or connect your GitHub repository

### Option 4: Deploy to Vercel
```bash
npm i -g vercel
vercel
```

### Option 5: Deploy to any static host
Upload `index.html` and `sw.js` to any static hosting service:
- AWS S3 + CloudFront
- Firebase Hosting
- Cloudflare Pages
- DigitalOcean App Platform

## API Keys Required

### OpenAI API Key (Optional)
Required only for AI-powered suggestions feature.

1. Go to [platform.openai.com](https://platform.openai.com)
2. Create an account and add payment method
3. Generate an API key
4. Enter the key in Settings within the app

**Note**: The API key is stored locally in your browser and is sent directly to OpenAI's servers. Never share your API key publicly.

### Speech Recognition
Uses the browser's built-in Web Speech API - no API key required.
- Works best in Chrome and Safari
- Requires microphone permission

## Browser Compatibility

| Feature | Chrome | Safari (iPad) | Firefox | Edge |
|---------|--------|---------------|---------|------|
| Core App | ✅ | ✅ | ✅ | ✅ |
| Camera | ✅ | ✅ | ✅ | ✅ |
| Speech Recognition | ✅ | ✅ | ❌ | ✅ |
| PDF Export | ✅ | ✅ | ✅ | ✅ |
| Service Worker | ✅ | ✅ | ✅ | ✅ |

## iPad Optimization

- Large touch-friendly buttons (minimum 44px)
- Responsive layout adapts to screen size
- Supports Apple Pencil for precise annotations
- "Add to Home Screen" creates standalone app experience
- Optimized for landscape orientation

## Usage Tips

1. **Taking Photos**: Use the Camera button or Upload to add photos
2. **Annotating**: Select a tool, then draw on the canvas
3. **Voice Memos**: Tap the microphone and speak clearly
4. **Moving Objects**: Use Select tool to move/resize elements
5. **Deleting**: Select objects and tap Delete or use keyboard
6. **Preview**: See how your sheet will look when printed
7. **Export**: Generate a high-quality PDF for printing

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Delete/Backspace | Delete selected objects |
| Escape | Deselect / Close modals |
| Ctrl/Cmd + S | Export PDF |

## File Structure

```
spec-sheet-app/
├── index.html    # Main application (self-contained)
├── sw.js         # Service worker for offline support
└── README.md     # This file
```

## Technologies Used

- **Fabric.js** - Canvas-based drawing and object manipulation
- **jsPDF** - PDF generation
- **html2canvas** - Canvas capture for PDF export
- **Web Speech API** - Voice recording and transcription
- **Service Workers** - Offline capability
- **OpenAI GPT API** - AI-powered suggestions

## License

MIT License - Feel free to modify and use for your projects.

## Troubleshooting

### Camera not working
- Ensure HTTPS or localhost
- Grant camera permission when prompted
- Try refreshing the page

### Speech recognition not working
- Use Chrome or Safari
- Grant microphone permission
- Check that Web Speech API is supported

### PDF export issues
- Allow pop-ups if download is blocked
- Try lower quality setting for large documents
- Ensure all images have loaded before exporting

### AI suggestions not working
- Verify your OpenAI API key is correct
- Check your API key has available credits
- Ensure internet connection is active

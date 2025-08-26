# 🎯 AI Presentation Generator

Transform your text into professional PowerPoint presentations using AI-powered content structuring and template styling.

🌐 **Live Demo**: [https://pptgenerator-production.up.railway.app/](https://pptgenerator-production.up.railway.app/)

## ✨ Features

- **Smart Text Analysis**: AI intelligently breaks down text into slide structure
- **Multi-AI Provider Support**: Works with OpenAI GPT-4, Anthropic Claude, and Google Gemini
- **Template Style Application**: Extracts and applies styles from your PowerPoint templates
- **Professional PPTX Generation**: Creates downloadable PowerPoint files
- **Real-time Preview**: See slide structure before generation
- **Secure Processing**: API keys never stored or logged

## 🚀 Quick Start

### Prerequisites

- Node.js 14.0.0 or higher
- npm or yarn
- API key from one of: OpenAI, Anthropic, or Google

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ai-presentation-generator.git
   cd ai-presentation-generator
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create project structure**
   ```bash
   mkdir public
   # Move the HTML file to public/index.html
   ```

4. **Start the server**
   ```bash
   npm start
   ```

5. **Open your browser**
   ```
   http://localhost:3001
   ```
   
   Or try the live demo: [https://pptgenerator-production.up.railway.app/](https://pptgenerator-production.up.railway.app/)

### Development Mode

For development with auto-restart:
```bash
npm run dev
```

## 📁 Project Structure

```
ai-presentation-generator/
├── server.js              # Backend API server
├── package.json           # Dependencies and scripts
├── public/
│   └── index.html         # Frontend application
└── README.md             # This file
```

## 🔧 How It Works

### Text Processing Pipeline
1. **AI Analysis**: Sends your text + guidance to chosen AI provider
2. **Intelligent Structuring**: Creates 5-12 slides based on content density  
3. **Content Mapping**: Identifies titles, bullet points, and slide types
4. **Smart Organization**: Detects intro, main content, and conclusion slides

### PowerPoint Generation
1. **Template Analysis**: Extracts styles, colors, fonts from uploaded template
2. **Content Application**: Maps AI-generated content to template layouts
3. **PPTX Creation**: Generates complete PowerPoint file with proper XML structure
4. **Download**: Provides ready-to-use presentation file

## 📖 Usage Guide

### Step 1: Input Content
- Paste any text (research papers, meeting notes, documentation, etc.)
- Optionally add guidance (e.g., "investor pitch deck", "technical training")

### Step 2: Configure AI
- Choose your preferred AI provider
- Enter your API key (securely processed, never stored)

### Step 3: Upload Template
- Drag & drop your PowerPoint template (.pptx or .potx)
- App will extract and apply the template's styling

### Step 4: Generate
- Click "Generate Presentation"
- Preview the slide structure
- Download your professional presentation

## 🔑 API Keys

Get your API keys from:

- **OpenAI**: https://platform.openai.com/api-keys
- **Anthropic**: https://console.anthropic.com/
- **Google AI**: https://makersuite.google.com/app/apikey

⚠️ **Security Note**: API keys are only used for the current session and are never stored or logged.

## 🛠 API Endpoints

### POST `/api/analyze`
Analyzes text content and generates slide structure.

**Request Body:**
```json
{
  "text": "Your content text...",
  "guidance": "Optional guidance for tone/structure",
  "provider": "openai|anthropic|gemini", 
  "apiKey": "your-api-key"
}
```

**Response:**
```json
{
  "success": true,
  "slides": {
    "presentationTitle": "Generated Presentation",
    "totalSlides": 8,
    "slides": [
      {
        "title": "Slide Title",
        "content": ["Point 1", "Point 2", "Point 3"],
        "type": "content",
        "notes": "Speaker notes"
      }
    ]
  }
}
```

### GET `/api/health`
Health check endpoint.

## 🎨 Customization

### Supported Input Types
- **Markdown**: Formatted text with headers and lists
- **Plain Text**: Any unstructured text content
- **Research Papers**: Academic or technical documents
- **Meeting Notes**: Bullet points and action items
- **Documentation**: Technical guides and manuals

### Presentation Types
- **Business Pitches**: Investor decks, sales presentations
- **Technical Training**: Educational and instructional content  
- **Academic Presentations**: Research findings and analysis
- **Project Updates**: Status reports and progress reviews
- **Marketing Content**: Product launches and campaigns

## 📋 Requirements

### System Requirements
- Node.js 14.0.0+
- 2GB RAM minimum
- Modern web browser (Chrome, Firefox, Safari, Edge)

### File Limitations
- Template files: Max 50MB
- Text input: Max 100KB
- Supported formats: .pptx, .potx

## 🚀 Deployment

### Local Development
```bash
npm run dev
```

### Production Deployment

**Heroku:**
```bash
git push heroku main
```

**Railway:**
```bash
railway deploy
```

**Vercel/Netlify:**
- Deploy as Node.js application
- Set build command: `npm install`
- Set start command: `npm start`

### Environment Variables
```
PORT=3001              # Server port (optional)
NODE_ENV=production    # Environment mode
```

## 🔧 Troubleshooting

### Common Issues

**"API request failed"**
- Check your API key is valid and has sufficient credits
- Verify the provider name is correct (openai/anthropic/gemini)

**"Template upload failed"**  
- Ensure file is .pptx or .potx format
- Check file size is under 50MB
- Try a different template file

**"No slides generated"**
- Verify input text has substantial content (minimum 100 words recommended)
- Check AI provider is responding correctly
- Try different guidance text

### Debug Mode
Set environment variable for detailed logging:
```bash
DEBUG=true npm start
```

## 📝 License

MIT License - see LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 🎉 Acknowledgments

- Built with Express.js and modern web technologies
- AI providers: OpenAI, Anthropic, Google
- PowerPoint file format based on Open XML standards

---

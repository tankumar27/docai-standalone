# DocAI - AI-Powered Document Analysis

A modern web application that allows users to analyze Google Docs content using AI. Simply paste a Google Docs URL and ask questions about the document using natural language.

## Features

- **Google Docs Integration**: Extract content from publicly shared Google Docs
- **AI-Powered Q&A**: Ask questions about document content using Gemini AI
- **Real-time Processing**: Fast document analysis and instant responses
- **Conversation History**: Track all questions and answers for each document
- **Quick Questions**: AI-generated suggested questions for each document
- **Modern UI**: Responsive design built with React and Tailwind CSS

## Setup Instructions

### 1. Install Dependencies

```bash
npm install
```

### 2. Environment Configuration

1. Copy the example environment file:
```bash
cp .env.example .env
```

2. Get your Google API key:
   - Go to [Google AI Studio](https://aistudio.google.com/)
   - Create a new project or select an existing one
   - Generate an API key for Gemini
   - Copy the API key

3. Add your API key to the `.env` file:
```
GOOGLE_API_KEY=your_google_api_key_here
NODE_ENV=development
```

### 3. Run the Application

```bash
npm run dev
```

The application will start on `http://localhost:5000`

## How to Use

1. **Share Your Google Doc**:
   - Open your Google Doc
   - Click "Share" in the top right
   - Change access to "Anyone with the link can view"
   - Copy the document URL

2. **Upload Document**:
   - Paste the Google Docs URL in the upload form
   - Click "Process Document"
   - Wait for the content to be extracted

3. **Ask Questions**:
   - Type your question in the text area
   - Click "Ask Question" or use one of the suggested quick questions
   - View the AI-generated answer in the conversation history

## Technical Architecture

### Frontend
- **React 18** with TypeScript
- **Tailwind CSS** for styling
- **Wouter** for routing
- **TanStack Query** for state management
- **React Hook Form** with Zod validation
- **Radix UI** components

### Backend
- **Node.js** with Express
- **TypeScript** with ES modules
- **Gemini AI** for document analysis
- **In-memory storage** for development
- **Google Docs API** for content extraction

### Project Structure
```
docai-standalone/
├── client/           # Frontend React application
│   ├── src/
│   │   ├── components/   # UI components
│   │   ├── pages/        # Page components
│   │   ├── hooks/        # Custom hooks
│   │   └── lib/          # Utilities
├── server/           # Backend Express application
│   └── services/     # External service integrations
├── shared/           # Shared types and schemas
└── package.json      # Dependencies and scripts
```

## API Endpoints

- `POST /api/documents/process` - Process a Google Doc URL
- `POST /api/conversations` - Ask a question about a document
- `GET /api/documents/:id/conversations` - Get conversation history
- `POST /api/documents/:id/quick-questions` - Generate quick questions

## Requirements

- Node.js 18+ 
- Google API key from Google AI Studio
- Internet connection for API calls

## Troubleshooting

### Document Access Issues
- Ensure the Google Doc is shared publicly ("Anyone with the link can view")
- Check that the URL is a valid Google Docs URL
- Verify the document exists and is accessible

### API Key Issues
- Make sure your Google API key is correct
- Ensure the key has access to Gemini AI services
- Check that the key is properly set in the `.env` file

### Build Issues
- Delete `node_modules` and run `npm install` again
- Ensure you're using Node.js 18 or higher
- Check that all dependencies are installed correctly

## License

This project is open source and available under the MIT License.
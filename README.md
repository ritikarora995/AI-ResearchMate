# 🔍 AI Research Assistant

> Intelligent research companion that leverages Google Gemini AI to automate content summarization and provide smart topic suggestions, helping researchers and students save time and discover new insights.

## 🌟 Overview

AI Research Assistant is a full-stack application that combines the power of Google's Gemini AI with a seamless browser-based interface. Simply highlight any text on a webpage, and get instant AI-powered summaries and related topic suggestions.

## ✨ Key Features

- **🤖 AI-Powered Summarization**: Automatically generate concise summaries of lengthy research content
- **💡 Intelligent Topic Analysis**: Discover related topics and research directions you might have missed
- **🚀 One-Click Access**: Chrome Extension provides instant access without leaving your research workflow
- **⚡ Real-Time Processing**: Fast, reactive backend handles multiple requests concurrently
- **🔒 Secure & Reliable**: Enterprise-grade error handling and input validation

## 🛠️ Tech Stack

### Backend
- **Java 17** - Core programming language
- **Spring Boot 3.4** - Application framework
- **Spring WebFlux** - Reactive programming for concurrent request handling
- **Google Gemini AI** - Generative AI for content analysis
- **Maven** - Build and dependency management

### Frontend
- **Chrome Extension (Manifest V3)** - Browser integration
- **JavaScript** - Extension logic and API integration
- **HTML/CSS** - User interface

## 🚀 Getting Started

### Prerequisites
- Java 17 or higher
- Maven 3.6+
- Google Gemini API Key ([Get it here](https://ai.google.dev/))
- Chrome Browser

### Installation

**Step 1: Clone the repository**
```bash
git clone https://github.com/yourusername/ai-research-assistant.git
cd ai-research-assistant/research-assistant
```

**Step 2: Configure API Key**

Create file `src/main/resources/application.properties` with:
```properties
gemini.api.url=https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key=
gemini.api.key=YOUR_GEMINI_API_KEY_HERE
server.port=8080
```

**Step 3: Build and Run Backend**
```bash
mvn clean install
mvn spring-boot:run
```

Backend will start at `http://localhost:8080`

**Step 4: Install Chrome Extension**
- Open Chrome and navigate to `chrome://extensions/`
- Enable "Developer mode" (toggle in top right)
- Click "Load unpacked" button
- Select the `research-assistant-ext` folder from the cloned repository
- Extension icon will appear in your browser toolbar

## 📖 Usage

1. **Navigate to any webpage** with content you want to analyze
2. **Highlight text** you want to summarize or analyze
3. **Click the extension icon** in your browser toolbar
4. **Choose an operation:**
   - **Summarize**: Get a concise summary of the content
   - **Suggest Topics**: Discover related research topics
5. **View AI-generated results** in real-time

## 🏗️ Architecture

```
┌─────────────────────┐
│  Chrome Extension   │  (Frontend - JavaScript)
│   (Manifest V3)     │
└──────────┬──────────┘
           │ REST API
           ▼
┌─────────────────────┐
│  Spring Boot App    │  (Backend - Java)
│   + Spring WebFlux  │
└──────────┬──────────┘
           │ HTTP Request
           ▼
┌─────────────────────┐
│  Google Gemini AI   │  (AI Processing)
└─────────────────────┘
```

## 🔧 API Endpoints

### POST `/api/research/process`

Process content with AI operations

**Request Body:**
```json
{
  "content": "Your text content here...",
  "operation": "summarize"
}
```

**Operations:**
- `summarize` - Generate content summary
- `suggest` - Suggest related topics

**Response:**
```json
"AI-generated summary or suggestions..."
```

## 🎯 Key Technical Highlights

- **Reactive Programming**: Spring WebFlux enables non-blocking, concurrent request handling
- **Modern Standards**: Uses Chrome Extension Manifest V3 and Spring Boot 3.4
- **AI Integration**: Seamless integration with Google's latest Gemini AI model
- **Production-Ready**: Includes exception handling, validation, and CORS configuration

## 📝 Project Structure

```
.
├── research-assistant/          # Spring Boot Backend
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/research/assistant/
│   │   │   │   ├── ResearchAssistantApplication.java
│   │   │   │   ├── ResearchController.java
│   │   │   │   ├── ResearchService.java
│   │   │   │   ├── ResearchRequest.java
│   │   │   │   └── GeminiResponse.java
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   └── pom.xml
│
├── research-assistant-ext/      # Chrome Extension Frontend
│   ├── manifest.json
│   ├── background.js
│   ├── sidepanel.html
│   ├── sidepanel.css
│   └── sidepanel.js
│
└── README.md
```

## 💡 Features Roadmap

- [ ] Add support for multiple AI models
- [ ] Implement user history and saved summaries
- [ ] Add citation generation in multiple formats (APA, MLA, Chicago)
- [ ] Export summaries as PDF
- [ ] Add dark mode for extension UI
- [ ] Support for multiple languages

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

**How to contribute:**
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

**Ritika Arora**
- GitHub: [@ritikarora995](https://github.com/ritikarora995)
- LinkedIn: [Your LinkedIn Profile](https://linkedin.com/in/ritikarora995)
- Email: ritikarora995@gmail.com

## 🙏 Acknowledgments

- [Google Gemini AI](https://ai.google.dev/) for providing the AI capabilities
- [Spring Framework](https://spring.io/) team for the excellent reactive programming support
- Chrome Extensions [documentation](https://developer.chrome.com/docs/extensions/) and community
- All contributors who help improve this project

## 📞 Support

If you have any questions or run into issues:
- Open an [issue](https://github.com/yourusername/ai-research-assistant/issues) on GitHub
- Check existing issues for solutions
- Reach out via email

## 🔒 Security

**Important**: Never commit your API keys to version control!

Add `application.properties` to `.gitignore`:
```
src/main/resources/application.properties
```

Use environment variables or configuration files that are gitignored for sensitive information.

## 📈 Performance

The application is designed to handle concurrent requests efficiently:
- Non-blocking I/O with Spring WebFlux
- Reactive streams for better resource utilization
- Optimized for multiple simultaneous AI requests

## 🧪 Testing

Run tests with:
```bash
mvn test
```

## 🚢 Deployment

### Backend Deployment
Can be deployed to:
- AWS (EC2, Elastic Beanstalk)
- Heroku
- Google Cloud Platform
- Azure

### Extension Publishing
To publish to Chrome Web Store:
1. Create a developer account
2. Prepare store listing (screenshots, description)
3. Package extension as ZIP
4. Submit for review

---

⭐ **If you find this project helpful, please consider giving it a star!**

Made with ❤️ by Ritik Arora

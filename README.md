# NextWork RAG Web Application

A modern **AWS Bedrock-based** Retrieval-Augmented Generation (RAG) web application that allows users to interact with a knowledge base about NextWork projects through an intelligent chatbot interface.

## 🏗️ Architecture Overview

This application leverages **AWS Bedrock** services to provide two distinct AI interaction modes:

- **Knowledge Base Mode**: Uses AWS Bedrock Knowledge Base with retrieval-augmented generation for project-specific queries
- **Direct AI Mode**: Direct interaction with AWS Bedrock's Llama 3 model for general conversations

## 🚀 Key Features

- **Dual AI Interaction Modes**
  - Knowledge Base RAG: Query specific NextWork project documentation
  - Direct AI Chat: General-purpose AI conversations using Llama 3
- **Modern Web Interface**: Clean, responsive design with dark theme
- **Real-time Chat**: Interactive chat interface with typing indicators
- **Project Portfolio**: Visual showcase of NextWork projects
- **AWS Integration**: Full integration with AWS Bedrock services

## 🛠️ Technology Stack

### Backend
- **FastAPI**: High-performance Python web framework
- **AWS Bedrock**: AI/ML services for model inference and knowledge base
- **AWS Bedrock Agent Runtime**: For knowledge base retrieval and generation
- **Boto3**: AWS SDK for Python integration
- **Uvicorn**: ASGI server for FastAPI

### Frontend
- **HTML5/CSS3**: Modern responsive web interface
- **Vanilla JavaScript**: Client-side interactivity
- **Jinja2**: Server-side templating

### AWS Services
- **AWS Bedrock Runtime**: Direct model invocation
- **AWS Bedrock Agent Runtime**: Knowledge base operations
- **AWS Bedrock Knowledge Base**: Document retrieval system

## 📋 Prerequisites

- Python 3.8+
- AWS Account with Bedrock access
- AWS CLI configured with appropriate permissions
- Virtual environment (recommended)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd nextwork-rag-webapp
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**
   Create a `.env` file in the root directory:
   ```env
   AWS_REGION=us-east-2
   MODEL_ID=meta.llama3-70b-instruct-v1:0
   KNOWLEDGE_BASE_ID=your_knowledge_base_id
   MODEL_ARN=arn:aws:bedrock:us-east-2::foundation-model/meta.llama3-70b-instruct-v1:0
   ```

## 🚀 Running the Application

### Option 1: Using the main FastAPI app
```bash
python -m uvicorn main:app --reload --host 127.0.0.1 --port 8000
```

### Option 2: Using the web application
```bash
python -m uvicorn web_app:app --reload --host 127.0.0.1 --port 8000
```

### Option 3: Direct execution
```bash
python web_app.py
```

The application will be available at `http://127.0.0.1:8000`

## 🔌 API Endpoints

### Knowledge Base Query
```
GET /bedrock/query?text=your_question_here
```
Queries the AWS Bedrock Knowledge Base for project-specific information.

**Example:**
```
http://127.0.0.1:8000/bedrock/query?text=what%20projects%20has%20the%20student%20done?
```

### Direct Model Invocation
```
GET /bedrock/invoke?text=your_question_here
```
Directly invokes the Llama 3 model for general AI conversations.

**Example:**
```
http://127.0.0.1:8000/bedrock/invoke?text=who%20is%20madonna
```

## 🏛️ Application Structure

```
nextwork-rag-webapp/
├── main.py              # Simple FastAPI app with knowledge base endpoint
├── web_app.py           # Full web application with UI
├── requirements.txt     # Python dependencies
├── templates/
│   └── index.html      # Main web interface
├── static/
│   └── style.css       # Application styles
└── venv/               # Virtual environment
```

## ⚙️ Configuration

### AWS Bedrock Setup

1. **Enable AWS Bedrock**: Ensure Bedrock is available in your AWS region
2. **Model Access**: Request access to Llama 3 models in AWS Bedrock console
3. **Knowledge Base**: Create and configure a Bedrock Knowledge Base with your documents
4. **IAM Permissions**: Ensure your AWS credentials have the following permissions:
   - `bedrock:InvokeModel`
   - `bedrock:RetrieveAndGenerate`
   - `bedrock-agent:RetrieveAndGenerate`

### Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `AWS_REGION` | AWS region for Bedrock services | `us-east-2` |
| `MODEL_ID` | Bedrock model identifier | `meta.llama3-70b-instruct-v1:0` |
| `KNOWLEDGE_BASE_ID` | Your Bedrock Knowledge Base ID | `ABC123DEF456` |
| `MODEL_ARN` | Full ARN of the Bedrock model | `arn:aws:bedrock:...` |

## 🎯 Use Cases

- **Student Portfolio**: Showcase NextWork project completions
- **Interactive Documentation**: Query project documentation through natural language
- **Learning Assistant**: Get help with specific project implementations
- **General AI Chat**: Use for broader technical discussions

## 🔍 Features Deep Dive

### Knowledge Base RAG Mode
- Retrieves relevant information from indexed NextWork project documentation
- Provides context-aware responses based on actual project content
- Ideal for specific questions about project implementations

### Direct AI Mode
- Direct access to Llama 3 model capabilities
- General-purpose conversational AI
- Useful for broader technical discussions and explanations

### Web Interface
- **Project Grid**: Visual showcase of completed NextWork projects
- **Chat Modal**: Floating chat interface with mode toggle
- **Responsive Design**: Works on desktop and mobile devices
- **Real-time Feedback**: Typing indicators and smooth interactions

## 🚨 Error Handling

The application includes comprehensive error handling for:
- AWS service errors (ClientError, BotoCoreError)
- Missing environment variables
- Model invocation failures
- Network connectivity issues

## 📱 Responsive Design

The application is fully responsive and optimized for:
- Desktop browsers
- Tablet devices
- Mobile phones

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is part of the NextWork learning platform. Please refer to NextWork's terms of service for usage guidelines.

## 🔗 Related Links

- [NextWork Learning Platform](https://learn.nextwork.org)
- [AWS Bedrock Documentation](https://docs.aws.amazon.com/bedrock/)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)

---

**Built with ❤️ using AWS Bedrock and FastAPI**

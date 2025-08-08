# 🤖 LLM Comparison & Evaluation Tool

A comprehensive Python tool for comparing Large Language Models (LLMs) across multiple providers using various prompting strategies. Supports both CLI and web interfaces for interactive evaluation and performance analysis.

## Documentaion:
https://medium.com/@abhayemani8/llm-labs-149b8174bd33

## 🌟 Features

### Multi-Provider Support
- **Groq**: High-performance LLM inference
- **Google Gemini**: Advanced AI capabilities
- **Ollama**: Local LLM deployment

### Advanced Prompting Strategies
- **Zero-shot**: Direct prompting without examples
- **One-shot**: Single example-based prompting
- **Few-shot**: Multiple example-based prompting
- **Chain-of-Thought (CoT)**: Step-by-step reasoning
- **ReAct**: Reasoning + Action prompting
- **Self-Ask**: Self-questioning approach
- **Tree-of-Thought**: Multi-path exploration
- **Instruction + Constraints**: Structured output control
- **Persona-based**: Role-playing with custom personas

### Comprehensive Metrics
- **Performance**: Response time, token usage
- **Quality**: Readability scores (Flesch Reading Ease)
- **Analysis**: Prompt classification and evaluation
- **Reporting**: Automated report generation with insights

### Dual Interface
- **CLI Mode**: Terminal-based interaction
- **Web Interface**: Modern Flask-based UI

## 📋 Requirements

### System Requirements
- Python 3.8+
- For Ollama: Local Ollama installation
- For Groq/Gemini: Valid API keys

## 🚀 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/MONARCH1108/LLM_Labs.git
cd llm-comparison-tool
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Install spaCy Language Model
```bash
python -m spacy download en_core_web_sm
```

### 4. Environment Setup
Create a `.env` file in the project root:
```env
GROQ_API_KEY=your_groq_api_key_here
GEMINI_API_KEY=your_gemini_api_key_here
```

### 5. Install Ollama (Optional)
For local LLM support:
```bash
# Visit https://ollama.ai/download for installation instructions
# Then pull models:
ollama pull llama3:latest
ollama pull mistral:latest
```

## 📁 Project Structure

```
llm-comparison-tool/
├── app.py                 # CLI interface
├── flask_app.py                  # Flask web interface
├── requirements.txt        # Python dependencies
├── .env                    # Environment variables
├── utils/
│   ├── __init__.py
│   ├── comparison.py       # Core comparison logic
│   ├── llms.py            # LLM provider interfaces
│   ├── prompts.py         # Prompting strategies
│   └── report_generator.py # Report generation
├── comparison_tools/
│   ├── __init__.py
│   ├── tokenizer.py       # Token counting utilities
│   └── prompt_classifier.py # Prompt classification
├── templates/
│   └── index.html         # Web UI template
├── reports/               # Generated reports
└── logs/                  # Application logs
```

## 🖥️ Usage

### CLI Mode

#### Single LLM Chat
```bash
python main.py
# Choose option 1 for single LLM chat
# Select provider, model, and prompting strategy
# Start interactive conversation
```

#### Comparative Evaluation
```bash
python main.py
# Choose option 2 for comparative evaluation
# Select multiple providers and models
# Choose prompting strategies
# Enter your question for comparison
```

### Web Interface

#### Start the Web Server
```bash
python app.py
```
Access the web interface at `http://localhost:5000`

#### Features Available in Web UI
- **Interactive Model Selection**: Browse available models
- **Real-time Ollama Status**: Check local model availability
- **Live Comparison**: See results as they generate
- **Report Download**: Export detailed performance reports
- **Visual Metrics**: Performance charts and statistics

## 🔧 Configuration

### API Keys Setup

#### Groq API
1. Visit [Groq Console](https://console.groq.com/)
2. Create an account and generate API key
3. Add to `.env` file

#### Google Gemini API
1. Visit [Google AI Studio](https://makersuite.google.com/)
2. Create project and generate API key
3. Add to `.env` file

### Model Configuration

#### Groq Models
- `llama3-8b-8192`
- `llama3-70b-8192`
- `mixtral-8x7b-32768`
- `gemma-7b-it`

#### Gemini Models
- `gemini-1.5-pro`
- `gemini-1.5-flash`
- `gemini-2.0-flash`

#### Ollama Models
```bash
ollama pull llama3:latest
ollama pull mistral:latest
ollama pull codellama:latest
ollama pull vicuna:latest
```

## 📊 Evaluation Metrics

### Performance Metrics
- **Response Time**: Latency in seconds
- **Token Usage**: Input/Output/Total tokens
- **Throughput**: Tokens per second

### Quality Metrics
- **Readability**: Flesch Reading Ease score
- **Structure**: Sentence and syllable counts
- **Prompt Classification**: Automatic categorization

### Comparative Analysis
- **Speed Comparison**: Response time rankings
- **Efficiency Analysis**: Token usage patterns
- **Quality Assessment**: Readability scores
- **Best Performer**: Overall performance winner

## 📈 Sample Output

```
📊 LLM Comparison Results:

🔹 GROQ (llama3-8b-8192) | Prompt: Chain of Thought
🧠 Prompt Type: Reasoning | Prompt Length: 45 words
🔢 Tokens - Input: 123 | Output: 256 | Total: 379
⏱️ Response Time: 2.3 seconds
📝 Response Length: 187 words
📚 Readability - Sentences: 12 | Syllables: 298 | Flesch Score: 65.4
```

## 🔍 Advanced Features

### Custom Persona Prompting
```python
# Example: Detective persona
role = "detective"
tone = "analytical"
style = "detailed"
# Automatically generates specialized prompts
```

### Automated Report Generation
- **Performance Summary**: Statistical analysis
- **Model Comparison**: Side-by-side metrics
- **Best Practices**: Recommendations based on results
- **Export Options**: TXT, JSON formats

### Error Handling & Logging
- **Comprehensive Logging**: All interactions logged
- **Error Recovery**: Graceful handling of API failures
- **Status Monitoring**: Real-time provider status

## 🛠️ Development

### Running Tests
```bash
python -m pytest tests/
```

### Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

### Code Style
- Follow PEP 8 guidelines
- Use type hints where applicable
- Add docstrings for functions
- Keep functions focused and modular

## 📝 API Reference

### Core Functions

#### `run_comparative_evaluation(providers_models, prompts, user_input)`
Runs comparative evaluation across multiple LLMs.

**Parameters:**
- `providers_models`: Dict of providers and their models
- `prompts`: Dict of prompt templates
- `user_input`: User question for evaluation

#### `query_groq_llm(user_input, model, prompt)`
Queries Groq LLM with specified parameters.

#### `query_gemini_llm(user_input, model, prompt)`
Queries Google Gemini with specified parameters.

#### `query_ollama_llm(user_input, model, prompt)`
Queries local Ollama model with specified parameters.

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Areas for Contribution
- Additional LLM providers
- New prompting strategies
- Enhanced metrics and analysis
- UI/UX improvements
- Documentation and examples

# Frontend (index.html)
## Key Features & Important Information

### 1. **Multi-Provider AI Support**
- **Groq**: Ultra-fast inference with specialized hardware for real-time applications
- **Gemini**: Google's advanced AI models with strong reasoning capabilities
- **Ollama**: Run models locally for complete privacy and control (requires local installation)

### 2. **Advanced Prompt Engineering Strategies**
- Zero Shot: Direct questions without examples
- Chain of Thought: Step-by-step reasoning for complex problems
- Few Shot: Learning from multiple examples
- Persona Based: Role-playing with customizable personas
- Self-Questioning, Tree of Thoughts, and more advanced techniques

### 3. **Dual Interface Modes**
- **Single LLM Chat**: Test individual models with real-time conversations
- **Comparative Evaluation**: Run the same question across multiple models and prompt strategies simultaneously for comprehensive analysis

### 4. **Real-Time Performance Analytics**
- Response time tracking and analysis
- Token usage estimation
- Chat statistics (message count, average response time)
- Model performance comparisons

### 5. **Local Model Support (Ollama Integration)**
- Complete privacy - models run entirely on your machine
- No internet required after initial setup
- Supports popular models like Llama 3, CodeLlama, Mistral
- API endpoint to check locally installed models: `/api/ollama-models`

### 6. **Export & Sharing Capabilities**
- Export chat histories as JSON files
- Generate comprehensive performance reports
- Share comparison results via URL
- Download detailed logs for analysis
- Save and load configuration presets

### 7. **Interactive UI/UX Features**
- Dark theme with glassmorphism effects
- Animated progress indicators during model testing
- Toast notifications for user feedback
- Auto-scroll chat interface with toggle
- Copy message functionality with one-click

### 8. **API Endpoints Required**
```
POST /api/single-chat          # Single model chat
POST /api/comparative-evaluation # Multi-model comparison
POST /api/generate-report      # Performance report generation
GET  /api/ollama-models        # List local Ollama models
GET  /api/get-log             # Retrieve comparison logs
GET  /api/prompt-templates    # Load available prompt strategies
```

### 9. **Setup Requirements**
- Modern web browser with ES6+ support
- Backend API server (endpoints listed above)
- For Ollama: Local Ollama installation and running service
- For Groq: API key and model access
- For Gemini: Google AI API credentials

### 10. **Built-in Help & User Guidance**
- Interactive welcome tour for first-time users
- Contextual help tooltips and information panels
- Sample questions categorized by use case (coding, reasoning, creative, analysis)
- Model validation and setup verification
- Comprehensive error handling with user-friendly messages

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

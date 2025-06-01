# 🔍 AI Company Research Assistant

A comprehensive AI-powered research tool that provides deep analysis of companies and industries using advanced language models and web search capabilities. This tool generates detailed reports including market analysis, AI recommendations, competitor insights, and implementation strategies.

## ✨ Features

### 🔐 **User Authentication**
- Secure login/registration system with SQLite backend
- Session management with "Remember Me" functionality
- Default admin account (username: `admin`, password: `admin123`)

### 🏢 **Company Research**
- **Multi-company analysis**: Research multiple companies simultaneously
- **Industry insights**: Comprehensive market trend analysis
- **AI use cases**: Generated AI implementation opportunities
- **Competitor analysis**: SWOT analysis and competitive positioning
- **Implementation planning**: Detailed phase-by-phase deployment strategies
- **Cost-benefit analysis**: ROI calculations and financial projections

### 📊 **Interactive Dashboards**
- **Real-time progress tracking**: Live updates during research process
- **Tabbed results**: Organized display of research findings
- **Interactive charts**: Plotly visualizations for cost-benefit analysis
- **Export capabilities**: PDF report generation with professional formatting

### 💾 **Data Management**
- **Intelligent caching**: Avoid duplicate research with 24-hour cache validity
- **Report history**: Access previously generated reports
- **SQLite database**: Persistent storage for users and cached reports

## 🏗️ Architecture

### **Multi-Agent Workflow**
The system uses a LangGraph-based workflow with specialized AI agents:

1. **Industry Research Agent** - Analyzes market trends and company positioning
2. **Use Case Generator Agent** - Identifies AI implementation opportunities
3. **AI Recommendation Agent** - Provides strategic AI adoption advice
4. **Resource Collector Agent** - Gathers relevant industry resources
5. **Competitor Analysis Agent** - Performs comprehensive competitive intelligence
6. **Implementation Planning Agent** - Creates detailed deployment roadmaps
7. **Cost-Benefit Agent** - Calculates financial impact and ROI

### **Technology Stack**
- **Frontend**: Streamlit with custom CSS styling
- **Backend**: Python with LangChain/LangGraph orchestration
- **Database**: SQLite for user management and caching
- **AI Models**: OpenRouter API (Llama 3.3) / Local LM Studio support
- **Web Search**: Tavily API for real-time information gathering
- **Visualization**: Plotly for interactive charts
- **PDF Export**: FPDF/ReportLab for report generation

## 🚀 Installation

### Prerequisites
- Python 3.8+
- API keys for:
  - OpenRouter (or local LM Studio setup)
  - Tavily API for web search

### Setup Steps

1. **Clone the repository**
```bash
git clone <repository-url>
cd ai-company-research
```

2. **Install dependencies**
```bash
pip install streamlit pandas python-dotenv fpdf2 matplotlib sqlite3 plotly
pip install langchain-groq langgraph langchain-openai tavily-python
pip install streamlit-lottie requests markdown logging
```

3. **Environment Configuration**
Create a `.env` file in the root directory:
```env
groq_api_key=your_groq_api_key_here
tavily_api_key=your_tavily_api_key_here
```

4. **Install AI Tools Dependencies**
Ensure you have the following custom tool modules in your `Tools/` directory:
- `industryResearchTool.py`
- `resourceCollectorTool.py`
- `useCaseGeneratorTool.py`
- `webSearchTool.py`
- `aiRecommendationTool.py`
- `competitorAnalysisTool.py`
- `costBenefitTool.py`
- `implementationPlanningTool.py`

## 🎯 Usage

### **Starting the Application**
```bash
streamlit run app1.py
```

### **First Time Setup**
1. Access the application at `http://localhost:8501`
2. Login with default credentials:
   - Username: `admin`
   - Password: `admin123`
3. Change the default password in Settings

### **Conducting Research**
1. **Navigate to Company Research**
2. **Enter company names** (comma-separated for multiple companies)
3. **Specify the industry** sector
4. **Click "Start Research"** and monitor real-time progress
5. **Review results** in organized tabs
6. **Download PDF reports** for offline reference

### **Managing Reports**
- **Past Reports**: View previously generated research
- **Settings**: Change passwords and manage cache
- **Export Options**: Download comprehensive PDF reports

## 📈 Research Output

Each company analysis includes:

### **📊 Core Analysis**
- **Key Offerings**: Company's main products/services
- **Market Trends**: Industry-wide developments and patterns
- **AI Recommendations**: Strategic AI implementation advice

### **💡 Implementation Strategy**
- **Use Cases**: Specific AI applications with objectives
- **Implementation Plans**: Phase-by-phase deployment strategies
- **Cost-Benefit Analysis**: Financial projections and ROI calculations

### **🏁 Competitive Intelligence**
- **Competitor Analysis**: SWOT analysis and market positioning
- **AI Maturity Scoring**: Assessment of AI adoption readiness
- **Competitive Positioning**: Market differentiation strategies

### **📚 Supporting Resources**
- **Resource Links**: Relevant industry articles and references
- **Research Sources**: Web search results and citations

## ⚙️ Configuration

### **AI Model Configuration**
The system supports multiple AI backends:

```python
# OpenRouter (Default)
llm = ChatOpenAI(
    model="meta-llama/llama-3.3-8b-instruct:free",
    base_url="https://openrouter.ai/api/v1",
    openai_api_key="your_openrouter_key"
)

# Local LM Studio (Alternative)
llm = ChatOpenAI(
    model="meta-llama-3.1-8b-instruct:2",
    base_url="http://127.0.0.1:1234/v1",
    api_key="lmstudio"
)
```

### **Database Configuration**
- **User Authentication**: SQLite with SHA-256 password hashing
- **Report Caching**: 24-hour cache validity with automatic cleanup
- **Session Management**: Configurable session timeout

### **UI Customization**
- **Custom CSS**: Enhanced styling with gradients and animations
- **Responsive Design**: Mobile-friendly interface
- **Interactive Elements**: Hover effects and smooth transitions

## 🔒 Security Features

- **Password Hashing**: SHA-256 encryption for user passwords
- **Session Management**: Secure session handling with timeout
- **Input Validation**: Protection against SQL injection and XSS
- **API Key Protection**: Environment variable configuration

## 📱 User Interface

### **Modern Design Elements**
- **Gradient Backgrounds**: Professional color schemes
- **Animated Progress**: Real-time research progress tracking
- **Interactive Tabs**: Organized information display
- **Responsive Cards**: Mobile-friendly component layout

### **User Experience**
- **Real-time Updates**: Live progress during research
- **Intuitive Navigation**: Clear sidebar navigation
- **Error Handling**: Graceful error messages and recovery
- **Accessibility**: Screen reader compatible design

## 🐛 Troubleshooting

### **Common Issues**

**API Connection Errors**
- Verify API keys in `.env` file
- Check internet connectivity
- Confirm API service status

**PDF Generation Issues**
- Install ReportLab for enhanced PDF support
- Check font availability for Unicode characters
- Verify file system permissions

**Database Errors**
- Ensure SQLite write permissions
- Check database file integrity
- Clear cache if corruption occurs

**Performance Issues**
- Monitor API rate limits
- Consider local LM Studio for faster processing
- Optimize concurrent research requests

## 🔄 Development

### **Adding New Research Agents**
1. Create new tool class in `Tools/` directory
2. Implement `_run()` method with state management
3. Add to workflow in `workflow.py`
4. Update `ResearchState` type definitions

### **Customizing UI Components**
- Modify CSS in `app1.py` main function
- Add new pages in sidebar navigation
- Extend database schema for additional features

### **API Integration**
- Support for additional AI model providers
- Integration with enterprise APIs
- Custom web search implementations


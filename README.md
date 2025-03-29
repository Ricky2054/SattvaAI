# SattvaAI: A Self-Explanatory LLM

![SattvaAI Logo](https://via.placeholder.com/150)

## 🌟 Overview

SattvaAI is an innovative self-explanatory LLM (Large Language Model) platform designed to democratize access to complex AI decision systems. Our solution makes AI technologies transparent and interpretable, bridging the gap between advanced machine learning algorithms and human understanding.

Originally developed for the Smart Bengal Hackathon (SBH-Sr)-2025 by Team Mind_Matrix under the AI/ML and NLP theme (PS No.: SBHRCCIIT037), SattvaAI provides multi-level explanations tailored to different knowledge levels, empowering users to comprehend the reasoning behind AI predictions and fostering informed decision-making.

## 🎯 Key Objectives

- **Democratize Access** to complex AI decision systems
- Make AI technologies **transparent and interpretable**
- **Bridge the gap** between advanced machine learning algorithms and human understanding
- Enable users to **comprehend reasoning** behind AI predictions
- Foster **informed decision-making** and responsible AI use

## 🚀 Features

### Security & Trust Layer
- **Bias & Toxic Content Detection** via RSA-FDH signatures
- **Dynamic Transparency Adjustment** based on risk assessment

### Ethical Explainability
- **Multi-perspective Insights** to mitigate cultural/regional biases
- **Clear Data Usage Disclosure** with opt-in/out mechanisms

### Adaptive Learning Engine
- **Iterative Prompt Optimization & Debugging**
- **Feedback Loop** that adjusts explanation complexity based on user comprehension

### Safety & Limitation Awareness
- **Red-teaming** for vulnerability detection
- **Safety Mechanisms** including disclaimers & confidence-based depth adjustment

### Cross-Modal Generation
- Converts technical details to **storytelling**
- Supports **text, audio, and visual explanation modalities**

## 💡 Novelty & Competitive Edge

### Enhanced Transparency
Unlike traditional "black box" models, SattvaAI integrates a self-explanatory mechanism that clearly breaks down AI decisions, making them understandable at multiple levels.

### Multi-Modal Explanations
By combining textual, visual, and data-driven insights, SattvaAI delivers comprehensive explanations, surpassing conventional uni-modal methods.

### Robust Trust Validation
Incorporates advanced bias detection, confidence scoring, and source citations, providing an extra layer of validation that current market offerings often lack.

## 🌍 Societal Benefits & Target Communities

### 1. Financial Inclusion
- Empowers loan applicants from underserved communities
- Helps users understand credit decision mechanisms
- Enables challenging unfair loan rejections
- Provides actionable insights to improve financial profiles

### 2. Healthcare Equity
- Assists patients in understanding disease risk assessments
- Particularly beneficial for medically underserved areas
- Helps individuals without medical expertise interpret complex health predictions
- Bridges knowledge gaps in healthcare decision-making

### 3. Digital Literacy
- Makes complex AI technology accessible to non-technical users
- Provides intuitive visualizations
- Offers multi-level explanations tailored to different knowledge levels
- Reduces technological intimidation

### 4. Trust Validation
- Includes confidence scores with all recommendations
- Provides data source citations
- Offers alternative viewpoints
- Allows independent verification of AI-generated information

## 🏗️ Architecture

![Architecture Diagram](https://via.placeholder.com/800x400)

Our modular architecture implements:
- **Frontend layer** for user interaction
- **Application layer** for business logic
- **Explanation engine** at the core
- **Model integration layer** for connecting various AI models
- **Security & validation components** throughout the stack

## 🔄 Data Flow

![Data Flow Diagram](https://via.placeholder.com/800x300)

1. User submits a query or request for explanation
2. The request is processed through security validation
3. The appropriate AI models are engaged
4. The explanation engine generates multi-level interpretations
5. Results are validated for bias and accuracy
6. User receives customized explanations with confidence metrics

## 🛠️ Technology Stack

### Frontend
- **React.js** (Open Source)
- **Tailwind CSS** (Open Source)

### Backend
- **Python** (Open Source)
- **FastAPI** (Open Source)

### AI Frameworks
- **Custom Transformer Model** (Built on open-source libraries like PyTorch/TensorFlow)

### Databases & Caching
- **PostgreSQL** (Open Source)
- **Redis** caching (Open Source)

### Deployment & Infrastructure
- **Kubernetes** (Open Source)
- **AWS** (Cloud service; pricing based on usage and tier)

### Additional Tools
- **Git/GitHub** for version control (Open Source)
- **Docker** for containerization (Open Source)

## 💻 Installation & Setup

### Prerequisites
- Python 3.8+
- Node.js 14+
- Docker
- Kubernetes (for production deployment)

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/mind-matrix/sattvaai.git
   cd sattvaai
   ```

2. **Set up backend**
   ```bash
   cd backend
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Set up frontend**
   ```bash
   cd ../frontend
   npm install
   ```

4. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env file with your configuration
   ```

5. **Run development servers**
   
   Backend:
   ```bash
   cd backend
   uvicorn app.main:app --reload
   ```
   
   Frontend:
   ```bash
   cd frontend
   npm start
   ```

### Docker Deployment

1. **Build Docker images**
   ```bash
   docker-compose build
   ```

2. **Run with Docker Compose**
   ```bash
   docker-compose up
   ```

### Production Deployment

For Kubernetes deployment, refer to the detailed instructions in the [deployment documentation](./docs/deployment.md).

## 📊 Usage Examples

### Basic Explanation Request

```python
import requests

response = requests.post(
    "https://api.sattvaai.com/explain",
    json={
        "model": "credit-decision",
        "input": {
            "income": 50000,
            "credit_score": 680,
            "debt_ratio": 0.4
        },
        "explanation_level": "detailed"
    }
)

print(response.json())
```

### Response Example

```json
{
  "decision": "approved",
  "confidence": 0.87,
  "explanation": {
    "summary": "Your loan was approved primarily due to your good credit score and manageable debt ratio.",
    "detailed": {
      "factors": [
        {
          "name": "credit_score",
          "importance": 0.65,
          "contribution": "positive",
          "explanation": "Your credit score of 680 is above our threshold of 650, indicating reliable repayment history."
        },
        {
          "name": "debt_ratio",
          "importance": 0.25,
          "contribution": "neutral",
          "explanation": "Your debt-to-income ratio of 0.4 is within acceptable limits, though reducing debt could improve future applications."
        },
        {
          "name": "income",
          "importance": 0.1,
          "contribution": "positive",
          "explanation": "Your income meets our minimum requirements for this loan product."
        }
      ]
    },
    "visualizations": {
      "factor_importance": "/api/visualizations/credit-decision/12345/factors",
      "decision_boundary": "/api/visualizations/credit-decision/12345/boundary"
    },
    "sources": [
      {
        "name": "Credit Score Guidelines v2.3",
        "date": "2024-05-15",
        "url": "https://internal.documentation.com/credit-guidelines-v2.3"
      }
    ]
  }
}
```

## 🧪 Testing

### Running Tests

```bash
# Backend tests
cd backend
pytest

# Frontend tests
cd frontend
npm test
```

### Code Quality Checks

```bash
# Backend
flake8 backend
black backend

# Frontend
cd frontend
npm run lint
```

## 📚 Documentation

Comprehensive documentation is available in the [docs](./docs) directory:

- [API Reference](./docs/api-reference.md)
- [Architecture Details](./docs/architecture.md)
- [Explanation Engine](./docs/explanation-engine.md)
- [Security Framework](./docs/security.md)
- [Deployment Guide](./docs/deployment.md)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](./CONTRIBUTING.md) for details on the process for submitting pull requests.

## 👥 Team

**Team Mind_Matrix**

| Name | College/University | Department | Position |
|------|-------------------|------------|----------|
| Ricky Dey | Techno International New Town | CSE | Team Leader |
| Tanuja Garai | Techno International New Town | AIML | Member |
| Sorbojit Mondal | Techno International New Town | CSE | Member |
| Ritam Jana | Techno International New Town | CSE | Member |

**Mentor**

| Name | College/University | Department |
|------|-------------------|------------|
| Dr. Nabanita Das | Techno International New Town | CSE |

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

For inquiries, please contact: team@mindmatrix.ai

---

*SattvaAI - Making AI Transparent and Accessible for Everyone*

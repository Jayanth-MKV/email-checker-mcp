# 📧 Email Checker MCP Starter

A starter project for building an email validation MCP (Model Context Protocol) server. This tool provides comprehensive email validation capabilities with both web interface and command-line functionality, serving as the foundation for a more advanced MCP implementation.

**🚀 This project is the foundation for developing an email-checker-mcp server that will integrate with AI models through the Model Context Protocol.**

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.0+-red.svg)](https://streamlit.io/)
[![MCP](https://img.shields.io/badge/MCP-Ready-green.svg)](https://modelcontextprotocol.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🌟 Features

- **🎨 Web Interface**: Beautiful Streamlit-powered web application
- **📊 Batch Processing**: Upload CSV/Excel files for bulk email validation
- **🔍 Dual Validation**: Format checking + SMTP verification
- **📈 Progress Tracking**: Real-time progress bars and status updates
- **💾 Export Results**: Download validation results as CSV
- **📱 Responsive Design**: Works on desktop and mobile devices
- **⚡ Fast Processing**: Optimized for handling large email lists
- **🛡️ Error Handling**: Robust error handling and timeout management
- **🔌 MCP Foundation**: Designed as a starting point for MCP server development

## 🎯 Model Context Protocol (MCP) Vision

This project serves as a foundation for building an email-checker-mcp server that will:

- **🤖 AI Integration**: Provide email validation capabilities to AI models
- **📡 Protocol Compliance**: Follow MCP specifications for seamless integration
- **🔧 Tool Exposure**: Expose email validation functions as MCP tools
- **📊 Structured Responses**: Return validation results in MCP-compatible formats
- **🔗 Model Connectivity**: Enable AI models to validate emails in real-time

## 🚀 Quick Start

### Option 1: Web Interface (Recommended)

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/email-validator-tool.git
   cd email-validator-tool
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Streamlit app**

   ```bash
   streamlit run streamlit_email.py
   ```

4. **Open your browser** and navigate to `http://localhost:8501`

### Option 2: Command Line

```python
from email.email_validate_script import check_email

# Validate a single email
is_valid, message = check_email("example@domain.com")
print(f"Valid: {is_valid}, Message: {message}")
```

## 📋 How It Works

### 1. Format Validation

Uses regex pattern matching to verify email structure:

- Contains exactly one `@` symbol
- Valid characters before and after `@`
- Proper domain format with TLD
- No invalid special characters

### 2. SMTP Verification

Performs actual SMTP checks:

- DNS MX record lookup
- SMTP server connection
- Recipient verification
- Graceful error handling

## 🔧 Installation

### Prerequisites

- Python 3.7 or higher
- Internet connection for SMTP verification

### Dependencies

```bash
pip install streamlit pandas dnspython
```

### From Source

```bash
git clone https://github.com/yourusername/email-validator-tool.git
cd email-validator-tool
pip install -r requirements.txt
```

## 📖 Usage Examples

### Web Interface

1. Upload a CSV/Excel file with email addresses
2. Select the column containing emails
3. Click "Validate Emails"
4. View results and download the report

### Command Line Script

```python
python email/email_validate_script.py
# Enter email when prompted
```

### Programmatic Usage

```python
from email.email_validate_script import check_email, is_email_format_valid

# Check format only
if is_email_format_valid("user@example.com"):
    print("Format is valid")

# Full validation
is_valid, message = check_email("user@example.com")
print(f"Email validation: {is_valid} - {message}")
```

## 📁 Project Structure

```
email-checker-mcp-starter/
├── streamlit_email.py          # Main Streamlit web application
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
├── LICENSE                     # MIT License
├── CONTRIBUTING.md             # Contribution guidelines
├── email/
│   ├── email_validate_script.py  # Core validation logic (MCP foundation)
│   └── emails.csv             # Sample email data
├── phone/
│   └── validate_phone.py      # Future phone validation
└── mcp-server/                # Future MCP server implementation
    ├── server.py              # MCP server entry point (planned)
    ├── tools.py               # MCP tool definitions (planned)
    └── schemas.py             # MCP response schemas (planned)
```

## 🎯 Validation Results

The tool provides detailed validation results:

| Column               | Description                                   |
| -------------------- | --------------------------------------------- |
| `format_valid`       | Boolean indicating if email format is valid   |
| `reachable`          | Boolean indicating if email passed SMTP check |
| `validation_message` | Detailed message about validation result      |
| `username`           | Username part of email (before @)             |
| `domain`             | Domain part of email (after @)                |

## ⚠️ Important Notes

### SMTP Validation Limitations

- **Not 100% reliable**: Many email providers block SMTP verification
- **Rate limiting**: Large lists may encounter rate limits
- **False negatives**: Valid emails might fail SMTP checks due to server policies
- **Timeout handling**: Long timeouts may indicate server restrictions

### Best Practices

- Use format validation as primary filter
- Treat SMTP results as additional indicators
- For critical applications, consider email confirmation workflows
- Respect rate limits and add delays for large batches

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Issues and Support

- **Bug Reports**: [Create an issue](https://github.com/yourusername/email-validator-tool/issues)
- **Feature Requests**: [Request a feature](https://github.com/yourusername/email-validator-tool/issues)
- **Documentation**: [Wiki](https://github.com/yourusername/email-validator-tool/wiki)

## 🔮 Roadmap

### Current Version (Starter)

- [x] Email format validation
- [x] SMTP verification
- [x] Web interface with Streamlit
- [x] Batch processing capabilities
- [x] CSV export functionality

### Upcoming MCP Integration

- [ ] **MCP Server Implementation**: Build compliant MCP server
- [ ] **Tool Definitions**: Define email validation tools for AI models
- [ ] **Protocol Handlers**: Implement MCP request/response handling
- [ ] **Schema Validation**: Ensure MCP-compatible data structures
- [ ] **AI Model Testing**: Test integration with popular AI models

### Future Enhancements

- [ ] Phone number validation
- [ ] Advanced email reputation checking
- [ ] Real-time API endpoints
- [ ] Database storage options
- [ ] Docker containerization
- [ ] Performance optimizations
- [ ] Extended MCP tool capabilities

## 🛠️ Building the MCP Server

This starter project provides the foundation for creating an MCP server. The core validation logic in `email/email_validate_script.py` can be wrapped in MCP-compliant tools to enable AI models to validate emails.

### Key Components for MCP Implementation:

1. **Tool Registration**: Register email validation functions as MCP tools
2. **Request Handling**: Process MCP requests and route to validation functions
3. **Response Formatting**: Format validation results according to MCP specifications
4. **Error Handling**: Provide meaningful error responses for invalid requests

## 📊 Screenshots

### Web Interface

![Email Validator Web Interface](docs/screenshots/web-interface.png)

### Validation Results

![Validation Results](docs/screenshots/results.png)

## 🙏 Acknowledgments

- [Model Context Protocol](https://modelcontextprotocol.io/) for the amazing protocol specification
- [Streamlit](https://streamlit.io/) for the web framework
- [dnspython](https://dnspython.readthedocs.io/) for DNS resolution
- [pandas](https://pandas.pydata.org/) for data manipulation

## 📚 MCP Resources

- [MCP Official Documentation](https://modelcontextprotocol.io/docs)
- [MCP GitHub Repository](https://github.com/modelcontextprotocol)
- [MCP Server Examples](https://github.com/modelcontextprotocol/servers)

## 📈 Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/email-validator-tool?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/email-validator-tool?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/email-validator-tool)

---

<div align="center">
  <b>🚀 Building the future of AI-powered email validation with MCP</b><br>
  <em>Made with ❤️ for the developer and AI community</em>
</div>

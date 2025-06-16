# 📧 Email Validator Tool

A comprehensive email validation tool with both web interface and command-line functionality. This tool validates email addresses using format checking and SMTP verification to determine if emails are properly formatted and potentially reachable.

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.0+-red.svg)](https://streamlit.io/)
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
email-validator-tool/
├── streamlit_email.py          # Main Streamlit web application
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
├── LICENSE                     # MIT License
├── .gitignore                 # Git ignore file
├── email/
│   ├── email_validate_script.py  # Core validation logic
│   └── emails.csv             # Sample email data
├── phone/
│   └── validate_phone.py      # Future phone validation (coming soon)
├── docs/
│   └── screenshots/           # Application screenshots
└── tests/
    └── test_email_validation.py  # Unit tests
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

- [ ] Phone number validation (in development)
- [ ] API endpoints for integration
- [ ] Database storage options
- [ ] Advanced email reputation checking
- [ ] Webhook notifications
- [ ] Docker containerization
- [ ] Build MCP
- [ ] CLI tool with more options

## 📊 Screenshots

### Web Interface

![Email Validator Web Interface](docs/screenshots/web-interface.png)

### Validation Results

![Validation Results](docs/screenshots/results.png)

## 🙏 Acknowledgments

- [Streamlit](https://streamlit.io/) for the amazing web framework
- [dnspython](https://dnspython.readthedocs.io/) for DNS resolution
- [pandas](https://pandas.pydata.org/) for data manipulation

## 📈 Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/email-validator-tool?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/email-validator-tool?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/email-validator-tool)

---

<div align="center">
  <b>Made with ❤️ for the developer community</b>
</div>

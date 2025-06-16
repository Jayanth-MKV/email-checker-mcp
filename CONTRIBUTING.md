# Contributing to Email Validator Tool

Thank you for your interest in contributing to the Email Validator Tool! We welcome contributions from the community and are grateful for your support.

## 🤝 How to Contribute

### Reporting Issues

- Use the [GitHub Issues](https://github.com/yourusername/email-validator-tool/issues) page
- Search existing issues before creating a new one
- Provide detailed information including:
  - Steps to reproduce
  - Expected behavior
  - Actual behavior
  - Environment details (OS, Python version, etc.)

### Suggesting Features

- Create a [Feature Request](https://github.com/yourusername/email-validator-tool/issues) issue
- Describe the feature in detail
- Explain the use case and benefits
- Consider providing mockups or examples

### Code Contributions

#### Development Setup

1. Fork the repository
2. Clone your fork locally
3. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   pip install -r requirements-dev.txt  # If available
   ```

#### Making Changes

1. Create a new branch for your feature:
   ```bash
   git checkout -b feature/your-feature-name
   ```
2. Make your changes
3. Test your changes thoroughly
4. Follow the coding standards below

#### Submitting Changes

1. Commit your changes with clear, descriptive messages
2. Push to your fork
3. Create a Pull Request with:
   - Clear description of changes
   - Reference to related issues
   - Screenshots if UI changes are involved

## 📋 Coding Standards

### Python Code Style

- Follow [PEP 8](https://pep8.org/) style guidelines
- Use meaningful variable and function names
- Add docstrings to functions and classes
- Keep functions focused and small
- Use type hints where appropriate

### Example:

```python
def validate_email_format(email: str) -> bool:
    """
    Check if email format is valid using regex.

    Args:
        email (str): Email address to validate

    Returns:
        bool: True if format is valid, False otherwise
    """
    if not email or not isinstance(email, str):
        return False

    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return bool(re.match(pattern, email))
```

### Commit Messages

- Use present tense ("Add feature" not "Added feature")
- Use imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit first line to 72 characters
- Reference issues and pull requests when applicable

Examples:

```
Add email batch validation feature

Fix SMTP timeout handling for large domains

Update documentation with new API examples

Closes #123
```

## 🧪 Testing

### Running Tests

```bash
python -m pytest tests/
```

### Writing Tests

- Add tests for new features
- Test edge cases and error conditions
- Maintain good test coverage
- Use descriptive test names

Example:

```python
def test_email_format_validation():
    """Test email format validation with various inputs."""
    assert is_email_format_valid("user@example.com") == True
    assert is_email_format_valid("invalid-email") == False
    assert is_email_format_valid("") == False
    assert is_email_format_valid(None) == False
```

## 📝 Documentation

### Code Documentation

- Add docstrings to all public functions and classes
- Use clear, concise language
- Include parameter types and return values
- Provide usage examples when helpful

### README Updates

- Update README.md if your changes affect usage
- Add new features to the feature list
- Update installation or setup instructions if needed

## 🔄 Review Process

### Pull Request Review

1. Automated checks must pass
2. Code review by maintainers
3. Testing on different environments
4. Documentation review

### What We Look For

- **Functionality**: Does it work as intended?
- **Code Quality**: Is it well-written and maintainable?
- **Testing**: Are there adequate tests?
- **Documentation**: Is it properly documented?
- **Compatibility**: Does it work across supported platforms?

## 🚫 What Not to Contribute

- Breaking changes without discussion
- Code that doesn't follow our standards
- Features without proper testing
- Plagiarized or copyrighted code
- Malicious or harmful code

## 📞 Getting Help

- **Discussion**: Use [GitHub Discussions](https://github.com/yourusername/email-validator-tool/discussions)
- **Chat**: Join our Discord/Slack (if available)
- **Email**: Contact maintainers directly for sensitive issues

## 🏆 Recognition

Contributors will be:

- Listed in the CONTRIBUTORS.md file
- Mentioned in release notes for significant contributions
- Given credit in documentation

## 📋 Development Workflow

1. **Issue Assignment**: Comment on issues you'd like to work on
2. **Development**: Create feature branch and implement changes
3. **Testing**: Ensure all tests pass and add new tests
4. **Documentation**: Update relevant documentation
5. **Review**: Submit PR and address feedback
6. **Merge**: Maintainers will merge approved PRs

## 🔧 Development Tools

### Recommended Tools

- **Code Editor**: VS Code with Python extension
- **Linting**: flake8, pylint
- **Formatting**: black, autopep8
- **Type Checking**: mypy
- **Testing**: pytest

### Pre-commit Hooks (Optional)

```bash
pip install pre-commit
pre-commit install
```

## 🎯 Areas Needing Help

We especially welcome contributions in:

- 📱 Phone number validation features
- 🔌 API endpoint development
- 🐳 Docker containerization
- 📊 Performance optimizations
- 🌍 Internationalization
- 📝 Documentation improvements
- 🧪 Test coverage expansion

## 📜 Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

---

Thank you for contributing to Email Validator Tool! 🙏

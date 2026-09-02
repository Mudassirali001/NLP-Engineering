# Contributing to NLP Engineering

Thank you for your interest in contributing! We welcome contributions from everyone.

## How to Contribute

### Reporting Bugs

Before creating bug reports, please check the issue list as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

* **Use a clear and descriptive title**
* **Describe the exact steps which reproduce the problem**
* **Provide specific examples to demonstrate the steps**
* **Describe the behavior you observed after following the steps**
* **Explain which behavior you expected to see instead and why**
* **Include screenshots and animated GIFs if possible**
* **Include your Python version and package versions**

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

* **Use a clear and descriptive title**
* **Provide a step-by-step description of the suggested enhancement**
* **Provide specific examples to demonstrate the steps**
* **Describe the current behavior and expected behavior**
* **Explain why this enhancement would be useful**

### Pull Requests

* Fill in the required template
* Follow the Python and project code style
* Document new code with docstrings
* End all files with a newline
* Avoid platform-dependent code

## Development Setup

1. **Fork the repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/nlp-engineering.git
   cd Week_5
   ```

2. **Create a new branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Install dependencies in development mode**
   ```bash
   pip install -r requirements.txt
   ```

4. **Make your changes**
   - Write clear, documented code
   - Add comments for complex logic
   - Follow existing code style

5. **Test your changes**
   ```bash
   python nlp_engineering.py
   ```

6. **Commit your changes**
   ```bash
   git add .
   git commit -m "Add descriptive commit message"
   ```

7. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

8. **Create a Pull Request**
   - Reference any related issues
   - Clearly describe what your changes do
   - Include any relevant details

## Code Style Guidelines

### Python Style Guide
- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) conventions
- Use 4 spaces for indentation
- Maximum line length: 100 characters
- Use descriptive variable and function names

### Naming Conventions
```python
# Variables and functions: lowercase_with_underscores
text_tokens = word_tokenize(text)

# Classes: PascalCase
class TextProcessor:
    pass

# Constants: UPPERCASE_WITH_UNDERSCORES
MAX_NGRAM_SIZE = 5
```

### Documentation
- Write clear docstrings for functions and classes
- Use type hints where applicable
- Comment complex logic
- Keep README updated with new features

Example:
```python
def extract_keywords(text, top_n=5):
    """
    Extract top keywords from text.
    
    Args:
        text (str): Input text to analyze
        top_n (int): Number of top keywords to return
        
    Returns:
        list: Top keywords sorted by frequency
    """
    # Implementation here
    pass
```

## Commit Message Guidelines

- Use present tense: "Add feature" not "Added feature"
- Use imperative mood: "Move cursor to..." not "Moves cursor to..."
- Limit the first line to 72 characters or less
- Reference issues and pull requests liberally after the first line

**Format:**
```
Add feature for keyword extraction

- Implement frequency-based extraction
- Add support for custom stopwords
- Include unit tests for new function

Fixes #123
```

## Additional Notes

### Issue and Pull Request Labels

* `bug` - Something isn't working
* `enhancement` - New feature or request
* `documentation` - Improvements or additions to documentation
* `good first issue` - Good for newcomers
* `help wanted` - Extra attention is needed

## Community

* Use clear and professional language
- Be respectful and constructive in discussions
- Thank contributors for their work
- Celebrate contributions and improvements

## Questions?

Feel free to open an issue with the `question` label if you have any questions about contributing.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to NLP Engineering!

# Contributing to ZestAPI

We welcome contributions to ZestAPI. This guide outlines how to set up your environment, follow our standards, and collaborate effectively with the maintainers.

## Development Setup

### Prerequisites
- Python 3.10 or higher
- Git

### Setup Development Environment
1. **Fork and Clone**

   ```bash
git clone https://github.com/madnansultandotme/zestapi-python.git
cd zestapi-python
```

2. **Create Virtual Environment**

   ```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install Dependencies**

   ```bash
pip install -r requirements.txt
pip install -e .  # Install in development mode
```

4. **Run Tests**

   ```bash
pytest test_package.py -v
```

## Development Workflow

### Branch Naming
- feature/description – New features
- bugfix/description – Bug fixes
- docs/description – Documentation updates
- refactor/description – Code refactors

### Commit Messages
Follow conventional commits:

```
type(scope): description

feat(auth): add JWT token refresh functionality
fix(routes): resolve path parameter parsing issue
docs(readme): update installation instructions
```

Accepted types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.

## Code Standards

### Python Code Style
- Follow PEP 8
- Format with `black .`
- Sort imports with `isort .`
- Maximum line length: 88 characters

### Type Hints
- Annotate all functions
- Use the `typing` module for composite types

```python
from typing import Any, Dict, List, Optional

def process_users(users: List[Dict[str, Any]]) -> Optional[str]:
    """Process user collection and return status."""
    # Implementation
    pass
```

### Documentation
- Provide docstrings for public functions and classes
- Use Google-style docstrings

```python
def create_user(name: str, email: str) -> Dict[str, Any]:
    """Create a new user with validation.

    Args:
        name: User's full name
        email: User's email address

    Returns:
        Dictionary containing user data

    Raises:
        ValueError: If email format is invalid
    """
    # Implementation
```

## Testing

### Writing Tests
- Place tests in `test_*.py` files
- Use `pytest`
- Cover success and failure scenarios

```python
import pytest
from zestapi import ZestAPI

def test_feature_description() -> None:
    """Test that feature works correctly."""
    app = ZestAPI()
    result = app.some_method()
    assert result == expected_value
```

### Running Tests

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=zestapi

# Run specific test file
pytest test_package.py -v
```

## Pull Request Process

### Before Submitting
- Format code: `black .`
- Sort imports: `isort .`
- Run tests: `pytest test_package.py`
- Update docs and add docstrings for new code
- Add tests for new functionality and ensure they pass

### PR Requirements
- Tests pass locally
- Code follows style guidelines
- Documentation is updated
- Self-review completed
- Commits are descriptive
- PR description explains the change

### PR Template
Use the template to cover:
- Change summary
- Linked issues
- Testing evidence
- Breaking changes (if any)

## Feature Development

1. **Create Issue** – Describe the feature, discuss approach, gather feedback.
2. **Implementation** – Create a feature branch, implement with tests, update documentation, follow standards.
3. **Integration** – Maintain backward compatibility, add migration notes if required, update changelog.

### Core Areas
- Routes and Routing: `zestapi/core/routing.py`
- Middleware: `zestapi/core/middleware.py`
- Authentication: `zestapi/core/security.py`
- Settings and Configuration: `zestapi/core/settings.py`

## Bug Reports

### Reporting Bugs
Include:
- Clear description
- Steps to reproduce
- Expected vs. actual behavior
- Environment details
- Code examples

### Fixing Bugs
1. Ensure an issue exists
2. Create a bugfix branch
3. Add a test that reproduces the bug
4. Fix the issue and verify the test passes
5. Open a PR

## Documentation Guidelines
- API docs: docstrings in code
- User guide: `docs/`
- Examples: `examples/`
- README: Project overview

Write for both new and experienced users, keep examples current, and use concise language.

## Community

### Communication
- GitHub Issues for bugs and features
- GitHub Discussions for questions
- Code reviews for shared learning

### Code of Conduct
- Be respectful and inclusive
- Focus on constructive feedback
- Support newcomers
- Celebrate contributions

## Release Process

### Version Numbering
Follow semantic versioning: `MAJOR.MINOR.PATCH`
- Major: Breaking changes
- Minor: Backward-compatible features
- Patch: Bug fixes

### Release Checklist
- Update version in `pyproject.toml`
- Update `CHANGELOG.md`
- Run full test suite
- Update documentation
- Create release tag
- Publish to PyPI

## Getting Help

### Resources
- Documentation: `docs/`
- Examples: `examples/`
- Issues: GitHub Issues
- Discussions: GitHub Discussions

### Questions
Before asking:
- Check documentation
- Search closed issues
- Review examples
- Read FAQ

When asking:
- Provide context
- Share code examples
- Specify environment details
- Describe what you tried

Thank you for contributing to ZestAPI.

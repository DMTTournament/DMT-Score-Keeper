# Contributing to HLL Tank Overwatch Bot

Thank you for your interest in contributing! This project is built for the Hell Let Loose community, and we welcome contributions from server owners, developers, and players.

## 🚀 Getting Started

### Development Setup

1. **Fork the repository**
2. **Clone your fork:**
   ```bash
   git clone https://github.com/StoneyRebel/HLL-Tank-Overwatch.git
   cd HLL-Tank-Overwatch
   ```
3. **Set up your environment:**
   ```bash
   cp .env.template .env
   # Fill in your test bot token and RCON credentials
   ```
4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
5. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## 📝 How to Contribute

### Bug Reports

If you find a bug, please create an issue with:
- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Bot logs if available
- Your environment (Railway, local, etc.)

### Feature Requests

For new features:
- Check existing issues first
- Describe the use case clearly
- Explain how it benefits the HLL community
- Consider implementation complexity

### Code Contributions

1. **Keep it focused:** One feature/fix per pull request
2. **Follow the existing style:** Use the same patterns as the current code
3. **Test thoroughly:** Make sure your changes work in different scenarios
4. **Update documentation:** Add/update comments and README if needed

## 🏗️ Code Guidelines

### Python Style
- Follow PEP 8 style guidelines
- Use descriptive variable names
- Add docstrings to functions and classes
- Keep functions focused and not too long

### Discord Bot Best Practices
- Always handle errors gracefully
- Use ephemeral responses for error messages
- Provide clear user feedback
- Don't spam the console with debug messages

### RCON V2 Integration
- Handle connection failures gracefully
- Add timeouts to all requests
- Log important events
- Close connections cleanly when done

## 🧪 Testing

### Local Testing
1. Set up a test Discord server
2. Use a real HLL server or mock the RCON responses
3. Test all bot commands and edge cases
4. Verify Railway deployment works

### Test Scenarios
- Bot startup with missing environment variables
- RCON connection failures
- Discord permission issues
- Auto-switch functionality
- Match end detection
- Time tracking accuracy

## 📦 Deployment

### Railway Compatibility
- Ensure your changes work on Railway
- Test environment variable handling
- Check that logs are visible in Railway dashboard
- Verify restart behavior

### Environment Variables
- Add new variables to `.env.template`
- Update documentation
- Provide sensible defaults
- Validate required variables on startup

## 🐛 Debugging

### Common Issues
- **RCON protocol changes:** Game updates may change RCON V2 responses
- **Discord API limits:** Be mindful of rate limits
- **Time zone handling:** Always use UTC for consistency
- **Memory usage:** Bot should be lightweight for Railway

### Logging
- Use appropriate log levels (INFO, WARNING, ERROR)
- Log important events but avoid spam
- Include context in error messages
- Don't log sensitive information (tokens, passwords)

## 📋 Pull Request Process

1. **Update documentation** if you change functionality
2. **Add environment variables** to the template if needed
3. **Test on Railway** or provide testing instructions
4. **Write clear commit messages** describing what and why
5. **Fill out the PR template** completely

### PR Checklist
- [ ] Code follows the style guidelines
- [ ] Changes are tested locally
- [ ] Documentation is updated
- [ ] Environment template is updated if needed
- [ ] No sensitive data is committed
- [ ] Railway deployment works (if applicable)

## 🎯 Priority Areas

We especially welcome contributions in these areas:

### High Priority
- Bug fixes for auto-switch functionality
- Performance improvements
- Better error handling and recovery
- Railway deployment improvements

### Medium Priority
- More detailed match statistics
- Enhanced Discord embed features
- Multi-language support

### Low Priority
- Code refactoring and cleanup
- Additional utility commands
- Alternative deployment methods
- Advanced configuration options

## 💬 Community

### Getting Help
- **GitHub Issues:** For bugs and feature requests
- **Discussions:** For questions and community chat

### Communication Guidelines
- Be respectful and constructive
- Help newcomers to HLL server management
- Focus on improving the HLL community experience

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

Thank you for helping make HLL tank warfare more competitive and fun! 🎯

# Company Brochure Generator

An AI-powered tool that automatically creates professional company brochures by analyzing website content. Perfect for generating marketing materials for prospective clients, investors, and potential recruits.

## Features

- **Intelligent Web Scraping**: Automatically extracts relevant content from company websites
- **Smart Link Detection**: Uses AI to identify and prioritize important pages (About, Careers, Company info)
- **AI-Powered Content Generation**: Creates professional brochures using advanced language models
- **Markdown Output**: Generates clean, formatted brochures in Markdown format
- **Customizable Tone**: Easy to modify for different brochure styles (professional, humorous, etc.)

## How It Works

1. **Web Scraping**: The tool scrapes the company's main website and extracts all text content
2. **Link Analysis**: Uses Gemini AI to intelligently identify relevant pages (about, careers, company info)
3. **Content Aggregation**: Gathers content from all relevant pages
4. **Brochure Generation**: Creates a comprehensive brochure using AI analysis of the collected content

## Prerequisites

- Python 3.7 or higher
- OpenAI API key
- Google API key (for Gemini)
- Virtual environment (recommended)

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/TiranVitharana/Company_Brochure_Generator.git
   cd company-brochure-generator
   ```

2. **Create and activate a virtual environment**:
   ```bash
   python -m venv llms
   source llms/bin/activate  # On Windows: llms\Scripts\activate
   ```

3. **Install required packages**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**:
   Create a `.env` file in the project root with your API keys:
   ```
   OPENAI_API_KEY=sk-proj-your-openai-key-here
   GOOGLE_API_KEY=your-google-api-key-here
   ```

## Usage

### Basic Usage

```python
from brochure_generator import create_brochure

# Generate a brochure for any company
create_brochure("HuggingFace", "https://huggingface.co")
create_brochure("Anthropic", "https://anthropic.com")
create_brochure("OpenAI", "https://openai.com")
```

### Command Line Usage

```bash
python brochure_generator.py
```

### Testing Individual Components

```python
# Test link extraction
from brochure_generator import get_links
links = get_links("https://anthropic.com")
print(links)

# Test website scraping
from brochure_generator import Website
site = Website("https://huggingface.co")
print(site.get_contents())
```

## Customization

### Changing the Brochure Tone

You can easily modify the system prompt to change the tone of the generated brochure:

```python
# For a humorous brochure
system_prompt = "You are an assistant that analyzes the contents of several relevant pages from a company website \
and creates a short humorous, entertaining, jokey brochure about the company for prospective customers, investors and recruits. Respond in markdown.\
Include details of company culture, customers and careers/jobs if you have the information."
```

### Modifying Content Length

Adjust the content truncation limit:

```python
user_prompt = user_prompt[:10_000]  # Increase from 5,000 to 10,000 characters
```

## API Configuration

The tool uses two AI models:
- **Gemini 2.5 Flash**: For link analysis and content processing
- **GPT-4o Mini**: As a fallback option

Make sure you have valid API keys for both services.

## Output Format

The tool generates brochures in Markdown format, typically including:
- Company overview
- Key products/services
- Company culture and values
- Career opportunities
- Target customers
- Investment highlights

## Error Handling

The tool includes basic error handling for:
- Invalid URLs
- Network connectivity issues
- API rate limits
- Missing environment variables

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Troubleshooting

### Common Issues

1. **API Key Issues**: Make sure your API keys are correctly set in the `.env` file
2. **Environment Issues**: Ensure you're running from an activated virtual environment
3. **Network Issues**: Some websites may block scraping attempts
4. **Rate Limits**: Be mindful of API rate limits when processing multiple companies

### Getting Help

If you encounter issues:
1. Check that all dependencies are installed
2. Verify your API keys are valid
3. Ensure your internet connection is stable
4. Try with a different company website

## Examples

### Sample Output

The tool generates professional brochures like:

```markdown
# HuggingFace Company Brochure

## About HuggingFace
HuggingFace is the leading platform for machine learning collaboration...

## Our Mission
Democratizing AI for everyone...

## Career Opportunities
Join our team of world-class researchers and engineers...
```

## Future Enhancements

- Support for additional output formats (PDF, HTML)
- Integration with more AI models
- Batch processing capabilities
- Enhanced error handling and logging
- Support for multi-language websites

---

**Note**: This tool is designed for educational and legitimate business purposes. Please respect website terms of service and robots.txt files when scraping content.

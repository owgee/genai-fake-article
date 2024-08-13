
# GenAI Fake Article Generator

## Project Overview

The **GenAI Fake Article Generator** is a tool that leverages generative AI models to create fake research articles, complete with realistic titles and abstracts. This project is designed to explore the capabilities of AI in generating coherent and contextually relevant academic content. It is intended for educational purposes, experimentation, and the development of AI-generated text.

## Features

- **Generate Research Titles**: The tool generates plausible research paper titles based on a given topic or keyword.
- **Generate Abstracts**: For each generated title, the tool creates a corresponding abstract that mimics the style and structure of real academic papers.
- **Customizable Models**: The project uses pre-trained models from the Hugging Face Transformers library, which can be fine-tuned for more specific outputs.

## Getting Started

### Prerequisites

- Python 3.x
- Virtual environment (optional but recommended)
- Git

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/owgee/genai-fake-article.git
   cd genai-fake-article
   ```

2. **Set Up the Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

### Project Structure

```
genai-fake-article/
├── data/                  # Directory for storing raw data (e.g., collected research papers)
├── models/                # Directory for storing trained models
├── scripts/               # Python scripts for data processing and model training
├── outputs/               # Generated titles and abstracts will be saved here
├── .gitignore             # Ignore unnecessary files and directories
├── README.md              # Project documentation
└── requirements.txt       # Python dependencies
```

### Usage

1. **Collect Data**:
   - Use the scripts in the `scripts/` directory to gather and preprocess data from sources like arXiv or PubMed.

2. **Generate Fake Articles**:
   - Run the main script to generate a fake research title and corresponding abstract:
   ```bash
   python scripts/generate_fake_article.py
   ```

3. **Evaluate Outputs**:
   - Review the generated outputs stored in the `outputs/` directory.

### Example

Here’s a quick example of how to generate a fake research paper:

```python
from transformers import pipeline

generator = pipeline('text-generation', model='gpt-2')

title = "Innovative Approaches in Machine Learning"
abstract = generator(f"Title: {title}\nAbstract:", max_length=200)[0]['generated_text']
print(abstract)
```

### Ethical Considerations

This project is for educational and experimental purposes only. The generated content should be clearly marked as fake to avoid any potential misuse or dissemination of misinformation. Please use this tool responsibly.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue to discuss potential improvements or features.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Hugging Face Transformers](https://github.com/huggingface/transformers) for the pre-trained models.
- arXiv and other public repositories for providing the data used for training.

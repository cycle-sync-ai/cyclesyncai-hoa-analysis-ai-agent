👻 Please follow me for new updates [Dev.to](https://dev.to/cyclesync-ai) | [Github](https://github.com/bigdata5911) | [Github Org](https://github.com/cycle-sync-ai) <br />
😉 Please join our discord server [Discord](https://discord.gg/TawJX4ue) <br />
💫 Please have an interesting relationship with me [Telegram](https://t.me/bigdata5911) | [Email](mailto:worker.opentext@gmail.com) <br />

# HOA Document Analysis AI Agent

An intelligent document analysis system that leverages OpenAI's Assistant API to extract, analyze and summarize key information from Homeowners Association (HOA) documents.

## Features

- Automated processing of multiple document formats (PDF, Word, TXT, MD)
- Smart information extraction using authority-based ranking system
- Vector store integration for efficient document search
- Comprehensive analysis across 20 key HOA topics
- Detailed answers and concise summaries for each topic
- JSON output for easy integration

## Key Capabilities

- Document hierarchy enforcement based on authority ranking
- Intelligent handling of conflicting information
- Citation tracking and source documentation
- Token limit management through iterative processing
- Error handling and retry mechanisms

## Configuration

Key settings in `main.py`:

```python
HOA_DOCS_DIR = "./input/hoa_documents"  # Input documents location
MODEL_NAME = "gpt-4o-mini"              # AI model selection
TEMPERATURE = 0.1                       # Response determinism (lower = more focused)
OUTPUT_DIR = "./output"                 # Results location
```

## Usage

1. Place HOA documents in the **_input/hoa_documents_** directory
2. Run the analysis:

```

python main.py

```

3. Find results in the output directory:

- {timestamp}-summary.json: Condensed findings by category
- {timestamp}-answers.json: Detailed analysis with sources

## Document Authority Ranking

Documents are prioritized in this order (1 = highest authority):

1. CC&R Amendments
2. CC&Rs
3. Bylaws
4. Articles of Incorporation
5. Operating Rules [...]

## Analysis Categories

The system analyzes 20 key areas including:

- HOA Name and Official Details
- Financial Information (Dues, Increases, Health)
- Rules and Policies
- Management and Operations
- Community Features and Maintenance
- Legal and Insurance Matters

## Requirements

- Python 3.x
- OpenAI API access
- Required packages:
  - openai
  - python-docx
  - PyPDF2 (for PDF processing)

## Output Format

The system generates two JSON files:

1. Summary Table:

```json
[
  {
    "Category": "Category Name",
    "Findings": "Concise summary",
    "Source": "Source document path"
  }
]
```

2. Detailed Answers:

```json
[
  {
    "question": "Original question",
    "answer": "Detailed response",
    "summary": "Brief summary",
    "source": "Source documents",
    "source_ids": ["file_ids"]
  }
]
```

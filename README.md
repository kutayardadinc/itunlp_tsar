# A Three-Stage Prompting Approach for CEFR-Oriented Text Simplification

A text simplification system developed for the TSAR 2025 Shared Task using a progressive prompting approach.

### Quick Start

1. Open `simplification.ipynb`
2. Update the API key in the first cell
3. Prepare your input data in JSONL format (see example below)
4. Update the file paths in the last cell
5. Run all cells to process your text

### Input Format

Your input file should be in JSONL format with the following structure:

```json
{"text_id": "example-1", "original": "The implementation of sophisticated algorithms enhances computational efficiency.", "target_cefr": "A2"}
{"text_id": "example-2", "original": "Photosynthesis is the process by which plants convert sunlight into energy.", "target_cefr": "A1"}
```

### Output Format

The system generates simplified texts in JSONL format:

```json
{"text_id": "example-1", "simplified": "Using smart computer programs makes computers work better and faster."}
{"text_id": "example-2", "simplified": "Plants use sunlight to make energy. This process is called photosynthesis."}
```

## System Architecture

The simplification process follows three sequential steps:

1. **Syntactic Simplification**

2. **Lexical Simplification**

3. **Elaboration**

## Configuration

The system uses GPT-4o with the following default configuration:

- **Model**: `gpt-4o-2024-11-20`
- **Temperature**: `0.5`
- **Top-p**: `0.95`
- **Max tokens**: `8192`

You can modify these settings in the `conversion_config` variable in the notebook.

## File Structure

```
├── simplification.ipynb          # Main notebook with simplification system
├── requirements.txt              # Python dependencies
├── README.md                    # This file
├── grammar/
│   └── grammar_rules.json       # CEFR grammar rules for each level
├── rules/
│   └── simplification_rules_en.json  # Simplification rules for each type and level
└── labeled_words/
    └── all_words.json          # CEFR word level mappings
```
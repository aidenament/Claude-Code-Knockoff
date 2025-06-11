# AI Agent Tool - Claude Code Knockoff

This project is an AI agent system that mimics the functionality of Claude Code, designed to analyze, edit, and explain Python projects. The main AI agent is powered by Google's Gemini AI and can interact with the included calculator project through a set of specialized functions.

## Project Structure

```
AI_Agent_Tool/
├── main.py                 # Main AI agent with Gemini integration
├── functions/              # Agent tool functions
│   ├── get_file_content.py # Read file contents
│   ├── get_files_info.py   # Explore directory structure
│   ├── run_python.py       # Execute Python files
│   └── write_file_content.py # Write/edit files
├── calculator/             # Sample project for AI agent to work with
│   ├── main.py            # Calculator CLI application
│   ├── pkg/
│   │   ├── calculator.py  # Core calculation logic
│   │   └── render.py      # Output formatting
│   └── tests.py           # Unit tests
└── requirements.txt       # Project dependencies
```

## How It Works

The AI agent in `main.py` operates as a Claude Code knockoff by:

1. **Accepting natural language prompts** via command line arguments
2. **Using specialized functions** to interact with the calculator project:
   - `get_files_info`: Explores project structure and file metadata
   - `get_file_content`: Reads and analyzes code files
   - `run_python_file`: Executes Python scripts and captures output
   - `write_file`: Creates or modifies files with new content

3. **Leveraging Gemini AI** to understand context, plan changes, and execute tasks
4. **Operating within a sandboxed environment** (limited to the calculator directory)

## Usage

### Prerequisites
- Python 3.7+
- Google Gemini API key set as `GEMINI_API_KEY` environment variable

### Installation
```bash
pip install -r requirements.txt
```

### Running the AI Agent
```bash
python main.py "your natural language request"
```

### Examples
```bash
# Analyze the calculator project
python main.py "analyze the calculator project structure"

# Add a new feature
python main.py "add a square root function to the calculator"

# Run tests and fix issues
python main.py "run the tests and fix any failing ones"

# Explain code functionality
python main.py "explain how the calculator evaluation works"
```

### Verbose Mode
Add `--verbose` flag to see detailed function calls and token usage:
```bash
python main.py "fix the calculator tests" --verbose
```

## Calculator Project

The included calculator project serves as a test subject for the AI agent. It features:

- **CLI Interface**: Accept mathematical expressions as command line arguments
- **Expression Evaluation**: Parse and calculate mathematical expressions
- **Formatted Output**: Clean presentation of calculations
- **Unit Tests**: Comprehensive test suite for validation

### Calculator Usage
```bash
cd calculator
python main.py "3 + 5 * 2"
```

## Features

- **Context-Aware**: Understands project structure and existing patterns
- **Code Quality**: Follows Python best practices and maintains consistency
- **Iterative Execution**: Can perform multi-step tasks with planning
- **Error Handling**: Robust error handling and validation
- **Security**: Sandboxed execution within the calculator directory

## System Architecture

The agent follows a structured approach:
1. **Analyze**: Explore codebase structure using `get_files_info`
2. **Understand**: Read relevant files with `get_file_content`
3. **Plan**: Break complex tasks into logical steps
4. **Execute**: Implement changes using `write_file`
5. **Verify**: Test changes using `run_python_file`

This creates a development workflow similar to Claude Code's capabilities while being constrained to work specifically with the calculator project.
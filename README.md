# n8n Assistant

This project contains a Multi-Channel Platform (MCP) server used to create an assistant integrated with n8n. The assistant can be used to search for n8n documentation, example workflows, and community forums.

## Features

- **Web Search**: Searches n8n documentation, workflows, and community forums based on a specific query.
- **HTML Content Fetching**: Uses BeautifulSoup to extract the main content from search results.
- **Asynchronous Processing**: Performs HTTP requests asynchronously, providing faster response times.

## Requirements

- Python 3.7 or higher
- `httpx` library
- `beautifulsoup4` library
- `python-dotenv` library

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file and add the necessary API keys:
   ```plaintext
   SERPER_API_KEY=your_api_key_here
   ```

## Usage

To start the assistant, run the following command:
```bash
uvicorn main:app --reload
```

Then, you can query the assistant for information related to n8n like this:
```python
await get_n8n_info("HTTP Request node", "docs")
```

## MCP Server

This project uses the `n8n-asistans` MCP server. The server is started with the following command:
```json
{
    "mcpServers": {
        "n8n-asistans": {
            "command": "uv",
            "args": [
                "--directory",
                "/n8n-assistant",
                "run",
                "main.py"
            ]
        }
    }
}
```

## Contributing

If you would like to contribute, please create a pull request or report issues.

## License

This project is licensed under the MIT License.
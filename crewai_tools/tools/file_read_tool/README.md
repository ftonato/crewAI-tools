# FileReadTool

## Description

The FileReadTool is a versatile component of the crewai_tools package, designed to streamline the process of reading and retrieving content from files. It is particularly useful in scenarios such as batch text file processing, runtime configuration file reading, and data importation for analytics. This tool supports various text-based file formats including `.txt`, `.csv`, `.json`, and adapts its functionality based on the file type, for instance, converting JSON content into a Python dictionary for easy use.

The tool also supports reading specific chunks of a file by specifying a starting line and the number of lines to read, which is helpful when working with large files that don't need to be loaded entirely into memory.

## Installation

Install the crewai_tools package to use the FileReadTool in your projects:

```shell
pip install 'crewai[tools]'
```

## Example

To get started with the FileReadTool:

```python
from crewai_tools import FileReadTool

# Initialize the tool to read any files the agents knows or lean the path for
file_read_tool = FileReadTool()

# OR

# Initialize the tool with a specific file path, so the agent can only read the content of the specified file
file_read_tool = FileReadTool(file_path='path/to/your/file.txt')

# Read a specific chunk of the file (lines 100-149)
partial_content = file_read_tool.run(file_path='path/to/your/file.txt', start_line=100, line_count=50)
```

## Arguments

- `file_path`: The path to the file you want to read. It accepts both absolute and relative paths. Ensure the file exists and you have the necessary permissions to access it.
- `start_line`: (Optional) The line number to start reading from (1-indexed). Defaults to 1 (the first line).
- `line_count`: (Optional) The number of lines to read. If not provided, reads from the start_line to the end of the file.

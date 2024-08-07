# Model Downloader Script

This script, `model_download.py`, facilitates the downloading of models from Hugging Face to a specified local directory. It handles authentication, branching, and checksum verification to ensure reliable and complete downloads.

## Features

- Download models from Hugging Face with support for authentication.
- Specify branches and files to download.
- Resume interrupted downloads.
- Verify file checksums to ensure data integrity.
- Multi-threaded downloads for improved speed.

## Prerequisites

- Python 3.6 or higher
- Required Python packages:
  - `requests`
  - `tqdm`
  - `huggingface_hub` (optional but recommended)

## Installation

1. Clone this repository or download the `model_download.py` script:

   git clone https://github.com/yourusername/your-repo.git
   cd your-repo

2. Install the required Python packages:

   pip install requests tqdm huggingface_hub

## Usage

To use the script, run it with the appropriate arguments. Below are some common usage scenarios.

### Download a Model

To download a model, specify the model name and optionally the branch:

   ```python model_download.py User/Model --branch 8_0```

### Command-Line Arguments

- `MODEL` (required): The model name, e.g., `Apel-sin/llama-3-8B-abliterated-v3-exl2`.
- `--branch` (optional): The branch name to download from (default is `main`).
- `--threads` (optional): Number of files to download simultaneously (default is 4).
- `--text-only` (optional): Only download text files (`txt`, `json`).
- `--specific-file` (optional): Download a specific file by name.
- `--output` (optional): Directory to save the downloaded model (default is `models`).
- `--clean` (optional): Start download from scratch (do not resume).
- `--check` (optional): Validate the checksums of the downloaded files.
- `--max-retries` (optional): Max retries for failed downloads (default is 5).

### Examples

1. **Download with Default Settings**

   ```python model_download.py Apel-sin/llama-3-8B-abliterated-v3-exl2```

2. **Specify a Branch**

   ```python model_download.py Apel-sin/llama-3-8B-abliterated-v3-exl2 --branch 8_0```

3. **Download to a Specific Directory**

   ```python model_download.py Apel-sin/llama-3-8B-abliterated-v3-exl2 --output /path/to/save```

4. **Only Download Text Files**

   ```python model_download.py Apel-sin/llama-3-8B-abliterated-v3-exl2 --text-only```

5. **Validate Checksums of Downloaded Files**

   ```python model_download.py Apel-sin/llama-3-8B-abliterated-v3-exl2 --check```

### Environment Variables

- `HF_USER`: Hugging Face username for authentication.
- `HF_PASS`: Hugging Face password for authentication.
- `HF_TOKEN`: Hugging Face API token for authentication (recommended).

## Troubleshooting

If you encounter issues, consider the following steps:

1. Ensure all required packages are installed.
2. Verify you have the correct model name and branch.
3. Check your internet connection.
4. Use the `--clean` flag to start the download from scratch if resuming fails.
5. Run the script with elevated privileges if there are permission issues.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License.

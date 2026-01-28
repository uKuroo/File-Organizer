# File Organizer Project

## Overview

A file monitoring application that observes a specified folder for new files and organizes them into designated folders based on their prefixes and extensions. The application is designed to automate the process of file management, making it easier to keep track of files.

## Project Structure

``` plaintext
paiton
├── src
│   ├── main.py          # Main application logic
│   ├── config/
│   │   ├── config.json  # Configuration file (auto-generated)
│   │   ├── data.py      # Configuration data structures
│   │   └── setup.py     # Configuration management and validation
│   └── log/             # Application logs
└── README.md            # Project documentation
```

## Installation

1. Clone the repository to your local machine.
2. Navigate to the project directory.
3. Run the application:

   ``` bash
   python src/main.py
   or
   python3 src/main.py
   ```

## Configuration

The application uses a JSON configuration file located at `src/config/config.json`.

On the first run, if the configuration file is missing, the application will automatically create a default one with sample paths. You should edit `src/config/config.json` to set your desired:

- **OBSERVED_FOLDER**: The directory to monitor for new files.
- **BASE_EXTENSION_FOLDER**: The root directory where organized files will be moved.
- **PREFIX_FOLDERS**: Rules for organizing files by name prefix
  - (the prefix will be separated by an underscore, ex: `PREFIX_FOLDERS = {"INF": "Informatica/"}` will move files like `INF_123.pdf` to `Informatica/123.pdf`).
- **EXTENSIONS_FOLDERS**: Rules for organizing files by extension.

The application validates the configuration structure on startup. If required fields are missing, it will ask if you want to reset to defaults or edit manually.

## Usage

To start monitoring the specified folder, run the `main.py` script:

``` bash
python src/main.py
or
python3 src/main.py
```

The application will continuously check for new files in the observable folder and move them to the appropriate destination based on their prefixes and extensions.

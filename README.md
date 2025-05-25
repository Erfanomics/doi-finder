# DOI Finder

This project retrieves DOIs (Digital Object Identifiers) for a list of article titles using the Crossref API. It reads article titles from a CSV file, queries Crossref for each title, and saves the results to a new CSV file.

## Features
- Reads article titles from a CSV file
- Uses string similarity to match titles with Crossref results. The script considers a DOI found if the title from Crossref is an exact match (similarity score of 1.0) to the input title.
- Retrieves and saves DOIs for matched articles
- Includes delays between API requests to minimize load on the Crossref server.

## Requirements
- Python 3.x
- pandas
- python-Levenshtein
- numpy

## Installation
Install the required packages with:
```bash
pip install -r requirements.txt
```

## Usage
1. Place your CSV file with article titles in this directory.
2. Update the notebook (`find doi based title.ipynb`) to use your CSV file path and the correct column name for titles.
    - For example, change `path_to_your_file.csv` to your actual input file path.
    - Replace `'titles'` in `pd.read_csv('path_to_your_file.csv')['titles'].tolist()` with the actual column name string from your CSV (e.g., `'Article Title'`).
    - Update the output file path `'your_file_path.csv'` in `df.to_csv('your_file_path.csv')` to your desired output file name.
3. Run the notebook from start to finish. The results (titles and DOIs) will be saved to a new CSV file.

## Output
- A CSV file containing the original titles and their corresponding DOIs (if found).

## Contributing
Contributions are welcome! Please open an issue or submit a pull request.

## License
MIT 
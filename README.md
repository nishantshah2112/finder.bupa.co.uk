# README

## Consultant Data Scraper

This Python project automates the process of scraping consultant information from Bupa Finder's website and stores the extracted data in an Excel file. The script leverages Selenium for dynamic content handling and BeautifulSoup for HTML parsing.

---

## Features

- **Dynamic Loading:** Automatically clicks the "Load More" button to fetch all available consultants.
- **Data Cleaning:** Removes extra spaces from fields like "Profession" and "Specialties."
- **Pagination Support:** Iteratively extracts data for multiple `rpp` values up to 250 for comprehensive scraping.
- **Export to Excel:** Saves the extracted data into separate sheets for each medical specialty.

---

## Installation

1. Clone the repository or download the script.
   ```bash
   git clone <repository_url>
   ```
2. Install required dependencies:
   ```bash
   pip install selenium beautifulsoup4 pandas xlsxwriter
   ```
3. Download the appropriate version of [ChromeDriver](https://chromedriver.chromium.org/) for your Chrome browser version.

4. Place the ChromeDriver executable in a known location, and update its path in the script:
   ```python
   service = Service(r"C:\path\to\chromedriver.exe")
   ```

---

## Usage

1. **Update URLs:**
   Add or modify the `links` dictionary in the script with the desired specialties and their corresponding URLs.
   ```python
   links = {
       "Anaesthetics": "<URL>",
       "Cardiology": "<URL>",
       # Add more specialties here
   }
   ```

2. **Run the Script:**
   Execute the script to start scraping:
   ```bash
   python consultant_scraper.py
   ```

3. **Output:**
   The extracted data will be saved as `consultants_data_rpp_cleaned.xlsx` in the current working directory, with each specialty stored on a separate sheet.

---

## Data Extracted

The following fields are extracted for each consultant:
- **Name:** Consultant's name.
- **Profession:** Professional title (cleaned for extra spaces).
- **Specialties:** Consultant's specialties (cleaned for extra spaces).
- **Phone:** Contact number.
- **Locations:** Practice locations.
- **Website:** Consultant's website link.

---

## Notes

- **Headless Mode:** The script uses Chrome in headless mode for better performance. To disable this, remove the `--headless` argument in the options configuration.
- **Dynamic rpp Support:** The script dynamically updates the `rpp` value in the URLs to fetch up to 250 records per request.
- **Error Handling:** The script handles scenarios where the "Load More" button is unavailable or no data is found for a given `rpp` value.

---

## Requirements

- Python 3.8+
- Google Chrome
- ChromeDriver
- Libraries:
  - `selenium`
  - `beautifulsoup4`
  - `pandas`
  - `xlsxwriter`

---

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute it as needed.

---

## Troubleshooting

1. **Invalid Escape Sequence Warnings:** Ensure that regex patterns use raw strings (e.g., `r"\s+"`) or the `re` module.
2. **ChromeDriver Version Mismatch:** Ensure the version of ChromeDriver matches your installed Chrome browser version.
3. **Timeout Errors:** Increase wait times (e.g., `time.sleep(3)`) if the website is slow to load.

---

## Contact

For queries or issues, contact [Nishant Shah](mailto:nishantshah2195@gmail.com).

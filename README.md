# Automated Documentation Link Validator using Gemini and Webdriver

This project provides an automated solution for validating URLs found within documentation topics. It leverages the capabilities of Gemini and Webdriver to check for broken links and ensure the integrity of your documentation. The `input_urls.csv` file included in this repository provides example URLs from `cloud.google.com/vmware-engine/docs`.

The primary goal is to help maintain high-quality, reliable documentation by proactively identifying and reporting problematic URLs.

### Technologies Used

*   **Gemini:** Google's multimodal AI model. It's utilized in this project to analyze the content or status of web pages accessed via URLs. For example, it can help determine if a page is a valid documentation page, an error page, or has other specific characteristics.
*   **Webdriver (Selenium):** A browser automation framework. Webdriver is used to programmatically open web pages in a browser, interact with them if necessary, and retrieve information such as page titles or HTTP status codes. This is essential for checking if a URL is live and accessible.
*   **Input URLs (`input_urls.csv`)**: This CSV file is where you list all the documentation topic URLs that you want to validate. The script will read this file and process each URL.

### Prerequisites

Before you can run this validator, ensure you have the following installed:

*   **Python 3.7+:** Download from [python.org](https://www.python.org/downloads/)
*   **pip (Python package installer):** Usually comes with Python.
*   **A compatible WebDriver:**
    *   For Chrome: [ChromeDriver](https://chromedriver.chromium.org/downloads)
    *   For Firefox: [GeckoDriver](https://github.com/mozilla/geckodriver/releases)
    *   Ensure the WebDriver executable is in your system's PATH or specify its location in your script.
*   **Required Python Libraries:** Install these using pip:
    ```bash
    pip install google-generativeai selenium pandas
    ```

### How to Run

1.  **Prepare your input URLs:**
    *   Open the **`input_urls.csv`** file.
    *   Ensure the first line is the header `URL`.
    *   List all the full URLs you want to validate, one URL per line, under the `URL` header.
    *   Save the file.

2.  **Configure your environment (if necessary):**
    *   Ensure your WebDriver (e.g., ChromeDriver) is accessible via your system's PATH.
    *   If you're using Gemini, you might need to set up authentication (e.g., API key). Refer to the `google-generativeai` library documentation for details. (Note: This part is a placeholder as I don't know the exact authentication mechanism used in the project).

3.  **Execute the script:**
    *   Open your terminal or command prompt.
    *   Navigate to the project directory.
    *   Run the main Python script (assuming it's named `validator.py` - I'll need to confirm the actual script name if it exists, or the user will have to create it).
        ```bash
        python validator.py
        ```

4.  **Review the results:**
    *   The script will process each URL from **`input_urls.csv`**.
    *   The output will indicate the status of each URL (e.g., valid, broken link, error page). The exact format of the output will depend on the script's implementation. (Note: This part is a placeholder as I don't know the script's output details).

### Structure of `input_urls.csv`

The `input_urls.csv` file should be a plain text CSV (Comma Separated Values) file with the following structure:

*   The first line **must** be the header: `URL`
*   Each subsequent line should contain a single, complete URL that you want the script to validate.

**Example:**

```csv
URL
https://cloud.google.com/vmware-engine/docs/environment/howto-forward-syslog
https://cloud.google.com/vmware-engine/docs/networking/howto-allocate-external-ip
https://docs.example.com/another/page
```
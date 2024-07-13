# Package Name Checker API

A Flask application to check the uniqueness of an app package name and fetch details from the Google Play Store. The application constructs a package name based on the provided app name and company name, and retrieves details if the app exists on the Play Store.

## Live Demo

The application is live at: [https://package-name-checker-api-1.onrender.com](https://package-name-checker-api-1.onrender.com)

## Features

- Construct app package names based on app and company names.
- Fetch details from the Google Play Store if the app exists.
- Return app name, developer name, app icon URL, app rating, number of reviews, and number of downloads.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/shishir1337/package_name_checker_api.git
    cd package-name-checker-api
    ```

2. Create a virtual environment and activate it:

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Run the Flask application:

    ```bash
    python app.py
    ```

2. The API will be accessible at `http://127.0.0.1:5000`.

## API Endpoints

### `POST /get_app_details`

Fetches app details from the Google Play Store based on the constructed package name.

#### Request

```json
{
    "app_name": "facebook",
    "company_name": "katana"
}
```

#### Response

If the app exists:

```json
{
    "package_name": "com.facebook.katana",
    "app_name": "Facebook",
    "developer_name": "Meta Platforms, Inc.",
    "app_icon_url": "https://example.com/icon.png",
    "app_rating": "4.2",
    "num_reviews": "1000000",
    "downloads": "1B+",
    "url": "https://play.google.com/store/apps/details?id=com.facebook.katana"
}
```

If the app does not exist:

```json
{
    "message": "Package name is unique!"
}
```

## Project Structure

```
package-name-checker-api/
│
├── app.py                  # Main Flask application
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
```

## Dependencies

- Flask
- Requests
- BeautifulSoup4

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to modify this template to better fit your project's specifics and requirements.

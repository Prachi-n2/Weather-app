# Weather App

Simple PyQt5 GUI that fetches current weather from OpenWeatherMap and displays temperature and an emoji.

## Requirements

- Python 3.8+
- `PyQt5`
- `requests`

## Run
Edit or provide your OpenWeatherMap API key.
Recommended: set an environment variable and modify weather%20app.py to read it via os.environ.get('OPENWEATHER_API_KEY').
Temporary (current PowerShell session):
$env:OPENWEATHER_API_KEY = "your_api_key_here"
python `weather%20app.py`
Or replace the api_key variable inside weather%20app.py (not recommended for production).

## Usage
Enter a city name and click Get Weather.
Temperature displays in °F with an emoji for weather conditions.

## Known issues & quick fixes
Widgets object names are all set on city_label. Fix by assigning each widget its own object name:
self.city_label.setObjectName("city_label")
self.city_input.setObjectName("city_input")
self.get_weather_button.setObjectName("get_weather_button")
self.temperature_label.setObjectName("temperature_label")
self.emoji_label.setObjectName("emoji_label")
self.description_label.setObjectName("description_label")

## Stylesheet selector and typo fixes:
Use QLineEdit#city_input instead of QLineEdit#city_label.
Use font-size: 30px; (lowercase px) and font-style: italic; (correct spelling).
Ensure emoji font family exists on Windows (e.g., Segoe UI Emoji).

## JSON keys:
Use data["weather"] (lowercase) not data["Weather"].
Consider reading the API key from environment:
import os and api_key = os.environ.get("OPENWEATHER_API_KEY")

## Troubleshooting
HTTP errors: check API key and city name.
Connection errors: check internet connection.
If GUI fonts or emoji don't render correctly, try a different system font.
Contributing
Open issues or PRs. Keep changes small and test on Windows with the PyCharm run configuration.

Install dependencies (Windows / PowerShell):
```powershell
python -m venv .venv
.\.venv\Scripts\Activate
pip install PyQt5 requests



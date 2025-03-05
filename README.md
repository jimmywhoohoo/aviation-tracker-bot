Installation
Bot Setup
Clone the Repository:

bash
Copy
Edit
git clone https://github.com/yourusername/aviation-tracker.git
cd aviation-tracker
Install Python Dependencies: Navigate to the bot directory and install the necessary dependencies:

bash
Copy
Edit
cd bot
pip install -r requirements.txt
Configure the Bot:

Create a .env file in the bot/ directory and add your Discord bot token and OpenSky API credentials:
ini
Copy
Edit
DISCORD_TOKEN=your-discord-bot-token
OPENAPI_USERNAME=your-opensky-username
OPENAPI_PASSWORD=your-opensky-password
Web App Setup
Navigate to the web Directory:

bash
Copy
Edit
cd web
Install Web App Dependencies: Install the required libraries for the web application:

bash
Copy
Edit
pip install -r requirements.txt
Configure the Web App:

Set up your Stripe API credentials.
Configure your database connection in web/config.py.
Run the Web App: You can run the web application locally with:

bash
Copy
Edit
flask run
Proxy Setup
To use proxies for API requests, edit the proxies.json file in the root of the project and add your proxy list.
Configuration
The bot can be configured using the config.py file inside the bot/ directory. Here you can define:

Proxy rotation settings
Logging configurations
Discord bot prefix and settings
OpenSky or ADS-B API keys and credentials
Example Configuration for OpenSky API:
python
Copy
Edit
API_USERNAME = "your-opensky-username"
API_PASSWORD = "your-opensky-password"
Running the Bot
To run the bot, execute the following command in the bot/ directory:

bash
Copy
Edit
python bot.py
Alternatively, you can use systemd to run the bot as a service on Linux. To set this up:

Copy the aviation_tracker.service file from the systemd/ directory to /etc/systemd/system/.
Reload systemd and enable the service:
bash
Copy
Edit
sudo systemctl daemon-reload
sudo systemctl enable aviation_tracker
sudo systemctl start aviation_tracker
Web App
The web app is a Flask application that allows users to manage their subscriptions and integrate the bot with their Discord servers.

Visit the Web App: After running the Flask app (flask run), you can access the web interface at http://localhost:5000/.

User Sign-Up and Subscription: Users can sign up, enter their Discord server details, and subscribe for $5 per month to use OpenSky API with proxy management.

Payment Handling: Payment is processed through Stripe, and users can manage their subscription through the web interface.

Usage
Discord Bot Commands
/plane ICAO24 [number] start: Start tracking a plane by its ICAO24 number.
/plane ICAO24 [number] stop: Stop tracking the plane.
/plane help: Get a list of available commands.
/plane status: Get the current status of the plane being tracked (location, altitude, etc.).
Web App Features
User Registration: Users can create accounts to access plane tracking.
Stripe Integration: Payment for OpenSky access.
Server Configuration: Add server details to start tracking planes.
Contributing
Contributions are welcome! Please feel free to fork this repository, submit pull requests, or open issues if you encounter any bugs or have feature suggestions.

License
This project is licensed under the MIT License - see the LICENSE file for details.







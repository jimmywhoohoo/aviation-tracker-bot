✈️ Aviation Tracker - Plane Monitoring Discord Bot & Dashboard
Aviation Tracker is a Discord bot that allows users to track planes in real time. With both OpenSky and ADS-B Exchange support, users can monitor takeoffs, landings, and even get screenshots of planes' live locations. It also comes with a web dashboard for easy management, including the ability to set up OpenSky credentials and manage your server settings.

Features
Track Planes: Use /track_plane ICAO24 to track a plane by its ICAO24 code.
Stop Tracking: Use /stop_plane ICAO24 to stop tracking a plane.
Live Map Screenshot: Get a live screenshot of the plane's location from globe.theairtraffic.com.
OpenSky & ADS-B Exchange: Supports two different plane tracking sources.
Web Dashboard: Set OpenSky credentials, manage your servers, and view plane activity.
Subscription Model: $5/month for access to the premium OpenSky API with proxy rotation for better data.
Admin & Moderation Tools: Only admins and mods can control tracking commands for each server.
Installation
1️⃣ Prerequisites
Python 3.10+
pip (Python's package installer)
Discord Bot Token (Get yours from Discord Developer Portal)
OpenSky Network Account (Optional)
Stripe Account (for premium subscription support)
2️⃣ Clone the Repository
Start by cloning this repository to your local machine:

bash
Copy
Edit
git clone https://github.com/yourusername/aviation-tracker.git
cd aviation-tracker
3️⃣ Install Dependencies
Next, install the required Python packages:

bash
Copy
Edit
pip install -r requirements.txt
4️⃣ Configure Environment Variables
Create .env files in both the bot and web directories:

Example for bot/.env
plaintext
Copy
Edit
DISCORD_TOKEN=YOUR_DISCORD_BOT_TOKEN
Example for web/.env
plaintext
Copy
Edit
SECRET_KEY=your_secret_key_here
STRIPE_SECRET_KEY=your_stripe_secret_key_here
STRIPE_PRICE_ID=your_stripe_price_id_here
5️⃣ Set Up Database
By default, the app uses SQLite for database storage. It will create the necessary files (bot/database.sqlite and web/database.sqlite) on the first run.

If you prefer to use PostgreSQL or MySQL, you can modify the database configurations in the bot/database.py and web/database.py files.

6️⃣ Running the Bot & Web Dashboard
Run the Discord Bot:
bash
Copy
Edit
cd bot
python3 bot.py
The bot should now be online and ready to accept commands on your Discord server.

Run the Web Dashboard:
bash
Copy
Edit
cd web
python3 app.py
You can access the web dashboard by navigating to http://localhost:5000.

📡 Bot Commands
Command	Description	Permissions
/track_plane ICAO24	Start tracking a plane	Admin/Mods
/stop_plane ICAO24	Stop tracking a plane	Admin/Mods
/plane_screenshot ICAO24	Take a screenshot of the plane's location	Admin/Mods
/set_opensky username password	Set OpenSky credentials	Admin/Mods
/show_opensky	Show OpenSky credentials status	Admin/Mods
🌐 Web Dashboard Features
Page	Description
/	Dashboard landing page
/login	Login/Register page (email required)
/servers	View and manage linked servers
/subscribe	Subscribe for premium access (Stripe)
⚙️ Configuration Files
bot/config.py
Modify this file to configure:

Data Source: Choose between opensky or adsb for tracking data.
Proxies: Enable or disable proxy rotation for premium accounts.
proxies.json
If you have access to proxies, you can list them here for proxy rotation:

json
Copy
Edit
[
    {"http": "http://proxy1:port"},
    {"http": "http://proxy2:port"}
]
💳 Premium Subscription
A premium subscription allows access to the OpenSky API with proxy rotation. To subscribe, use the Stripe payment system integrated with the web dashboard.

🧰 Running as a Service (Optional)
For better management, you can run the bot as a service using systemd on Linux.

Create a systemd service file at /etc/systemd/system/aviation_tracker.service:
ini
Copy
Edit
[Unit]
Description=Aviation Tracker Discord Bot
After=network.target

[Service]
User=youruser
WorkingDirectory=/path/to/aviation-tracker/bot
ExecStart=/usr/bin/python3 /path/to/aviation-tracker/bot/bot.py
Restart=always

[Install]
WantedBy=multi-user.target
Reload systemd and start the service:
bash
Copy
Edit
sudo systemctl daemon-reload
sudo systemctl enable aviation_tracker
sudo systemctl start aviation_tracker
🧑‍💻 Contributing
Fork this repository
Clone your fork
Create a new branch (git checkout -b feature-name)
Commit your changes (git commit -am 'Add new feature')
Push to the branch (git push origin feature-name)
Open a pull request
⚠️ Security & Privacy
Never hard-code sensitive keys directly in the code. Use .env files to manage environment variables securely.
Be cautious when using proxies or third-party APIs to avoid data breaches or misuse.
📞 Contact
For support, please contact:

[Your Support Email]
Join our Discord: [Your Discord Invite Link]
🚀 Ready to Track Planes?
Once everything is set up, you can invite the bot to your server, set your OpenSky credentials, and start tracking planes in real-time!








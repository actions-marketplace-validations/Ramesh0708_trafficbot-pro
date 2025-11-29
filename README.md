🚦 TrafficBot Pro

Automated city traffic alerts delivered to Microsoft Teams using GitHub Actions.

TrafficBot Pro fetches real-time traffic news from trusted sources, filters and summarizes it, adds severity indicators, includes a live Google Maps link for your city, and posts everything directly to your Microsoft Teams channel — fully automated on schedule.

Perfect for teams, offices, commuters, and IT operations groups who rely on regular traffic visibility.

--------------------------------------------------------------

✨ Features

🌍 Multi-city support (choose ANY city)

🤖 AI-style quick summaries based on keyword rules

🔴🟡🟢 Severity markers for each news headline

🗺️ Google Maps live traffic (auto-centered to chosen city)

🔁 50+ rotating fun facts to keep updates fresh

⏱️ Fully automated using GitHub Actions schedule

💸 Zero server cost (runs completely on GitHub Actions)

🔌 Easy plug-and-play setup with only 1 secret required

📩 Microsoft Teams webhook support

------------------------------------------------------------------------

🚀 Example Workflow

Create .github/workflows/trafficbot.yml:

name: TrafficBot Pro

on:
  schedule:
    - cron: "0 3 * * *"   # 8:30 AM IST
  workflow_dispatch:

jobs:
  traffic:
    runs-on: ubuntu-latest
    steps:
      - name: Run TrafficBot Pro
        uses: Ramesh0708/trafficbot-pro@v1
        with:
          city: "Pune"   # Change to any city (e.g., Mumbai, Bangalore, New York)
          webhook: ${{ secrets.TEAMS_WEBHOOK_URL }}

----------------------------------------------------------------------

🔧 Inputs
Input Name	Required	  Description
city	       ✅ Yes	  City name for traffic updates (e.g., Pune, Mumbai, Delhi, London)
webhook	     ✅ Yes     Microsoft Teams Incoming Webhook URL


--------------------------------------------------------------

💬 Output Example (Microsoft Teams)
🚦 TrafficBot Pro • 28 Nov 2025 • 10:42 AM
🌇 Evening traffic update — plan ahead!

• 🔴 Navale Bridge accident… (link)
• 🟢 Pune announces new one-way routes… (link)
• 🟡 Metro construction causing slowdowns… (link)

🔍 Summary: Roadworks causing slowdowns in multiple areas.

🗺️ Live Map: Baner Traffic Map  
🎉 Fun Fact: Hinjewadi Phase 3 sees surge every Monday morning.

----------------------------------------------------------------

🧩 How It Works

Collects traffic news via RSS from top publishers

Filters out old or duplicate articles

Adds severity markers

Generates a one-line smart summary

Appends a city-specific Google Maps traffic link

Sends everything to Microsoft Teams using your webhook

Logs archived results for your reference



🔐 Setup Required

Go to your repository

Open Settings → Secrets → Actions

Add new secret:

TEAMS_WEBHOOK_URL = Your Teams incoming webhook

That’s it! Your bot is fully automated.



📝 License

This project is licensed under the MIT License.



⭐ Support the Project

If you find TrafficBot Pro useful:

⭐ Star the repository

🐙 Share it with your team

💬 Provide feedback to improve it

🔄 Contribute pull requests

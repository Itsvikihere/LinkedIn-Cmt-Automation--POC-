💬 LinkedIn Auto Commenter (Selenium + Python)
This project automates LinkedIn commenting using Selenium WebDriver in Python. It:

Loads LinkedIn using your exported login cookies.

Navigates to your feed or a specific post URL.

Scrolls through posts to load more.

Detects who interacted with the post (like, comment, celebrate, etc.).

Parses their names and converts them to LinkedIn-style tags (e.g., @John Doe).

Posts a comment by combining the tagged names and your custom message.

✅ Helpful for engagement automation, marketing campaigns, and tagging connections on professional content.

🧰 Requirements
Python 3.8+

Google Chrome browser installed

chromedriver compatible with your Chrome version

LinkedIn account (manually logged in to export cookies)

📁 Folder Structure
pgsql
Copy
Edit
linkedin-auto-commenter/
│
├── script.py              # Main automation script
├── config.txt             # Configuration file
├── cookies.json           # LinkedIn cookies (manually exported)
├── comments.txt           # File containing comment text (only first line used)
├── output.log             # Generated log file during execution
└── chromedriver.exe       # ChromeDriver binary (optional if path set)
✍️ Step-by-Step Setup
✅ Step 1: Install Required Python Packages
Run this command to install required packages:

bash
Copy
Edit
pip install selenium webdriver-manager
⚙️ Step 2: Prepare config.txt
Create a file named config.txt with exactly 5 lines in this order:

less
Copy
Edit
1. Chromedriver path (example: C:/path/to/chromedriver.exe)
2. LinkedIn login URL (example: https://www.linkedin.com/login)
3. After-login URL (example: https://www.linkedin.com/feed/)
4. Scroll count (example: 5)
5. Number of posts to comment (example: 10)
Example config.txt:

bash
Copy
Edit
C:/Users/user/Downloads/chromedriver.exe
https://www.linkedin.com/login
https://www.linkedin.com/feed/
5
10
🔐 Step 3: Export Your LinkedIn Cookies
🔸 Option 1: Use Chrome Extension
Install this Chrome extension: EditThisCookie

Log in to your LinkedIn account manually.

Click the extension → Export cookies → Copy the JSON.

Paste it into a file named cookies.json in your project folder.

💬 Step 4: Prepare comments.txt
Create a file comments.txt and write your comment in the first line. This comment will be posted automatically.

Example:

rust
Copy
Edit
Great insights! Thanks for sharing.
🚀 Step 5: Run the Script
Open terminal in the project directory and run:

bash
Copy
Edit
python script.py
The script will do the following:

Open LinkedIn login page.

Add cookies from cookies.json.

Refresh and log you in.

Go to your target URL (post_login_url).

Scroll n times down and up to load more posts.

For each post:

Detect if someone liked/commented/supported.

Convert their names to @Name tags.

Insert comment and tagged users into the comment box.

Post it.

📓 Notes & Features
✅ Uses logging to write detailed log messages to output.log.

✅ Handles posts with and without reactions differently (function_a and function_b).

✅ Includes error handling for missing elements (comment box, dropdown, etc.).

✅ Uses webdriver_manager for managing ChromeDriver if desired.

🧪 Example Use Case
Imagine you want to:

Post “Thanks for sharing this!” on 10 posts in your feed.

Tag the first person who liked/commented on each post.

This script handles that with just a few lines of config and your comment.

⚠️ Disclaimer
Do NOT spam or overuse this bot — LinkedIn may restrict or ban your account.

Use this only on your own account and only for ethical engagement.

Make sure to read LinkedIn's Terms of Service before using.

🧑‍💻 Developer Note
This script is built with:

✅ Selenium

✅ webdriver-manager

✅ Python 3.x

✅ Works on Windows/Mac/Linux (ensure correct ChromeDriver path)

📞 Need Help?
Feel free to ask me to:

Add a GUI interface

Convert to headless mode (background run)

Schedule it daily

Extend it to like, repost, or connect

Happy automating! 🚀

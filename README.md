# Roblox Badge Cleaner

Just a small project, feel free to check it out

---

## Features

- Bulk badge deletion  
- Game-based exemptions  
- Keyword-based filtering  
- Built-in rate limiting (avoids API issues)   

---

## Example Output
[OK] 123456789 | 12/340
[SKIP] 987654321 (keyword)
[FAIL] 456789123 (403)

cooldown 60s...

Done. Deleted: 320 | Failed: 5 | Total: 325

---

## Requirements

- Python **3.10+**
- Roblox `.ROBLOSECURITY` cookie

Install dependencies:
pip install requests

---

### Environment Variables

| Variable         | Required | Description                              |
|-----------------|----------|------------------------------------------|
| ROBLOSECURITY   | ✅       | Your Roblox auth cookie                  |
| USERID          | ✅       | Your Roblox user ID                      |
| GAMES_EXEMPT    | ❌       | Comma-separated game IDs to ignore       |
| KEYWORDS_EXEMPT | ❌       | Skip badges containing these words       |

---

## Usage

once filling in the .env with your cookie and uid just run the main py file

python main.py

---

## How It Works

- Fetches all badges from your account (paginated)
- Filters based on:
  - Game ID
  - Keywords in name/description
- Deletes remaining badges in batches
- Pauses automatically every 30 deletions to avoid new roblox rate limits

---

## Warning

- **Badge deletion is permanent**
- There is **no undo**
- Make sure your exemptions are correct before running

---

## Disclaimer

This project uses Roblox’s internal APIs.  
It may break at any time if Roblox changes their endpoints.

Use at your own risk, as of posting this it functions correctly. if roblox add some form of detection then you are responsible for your account.

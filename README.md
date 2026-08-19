# Birthday Reminder Project  

![GitHub stars](https://img.shields.io/github/stars/i252010-ops/Birthday-Reminder-Project?style=flat) ![GitHub forks](https://img.shields.io/github/forks/i252010-ops/Birthday-Reminder-Project?style=flat) ![Python](https://img.shields.io/badge/language-Python-blue?style=flat)  

A simple, cross‑platform Python utility that tracks birthdays and sends timely reminders (via email or console) so you never miss a special day again.

---  

## Features  

- **Add / edit / delete** birthdays via a friendly CLI.  
- Store data in a lightweight **SQLite** database (no external DB required).  
- Configurable reminder **lead time** (e.g., 1 day, 1 hour).  
- **Email notifications** using SMTP (supports Gmail, Outlook, custom servers).  
- **Daily scheduler** that runs in the background (systemd service, cron, or Windows Task Scheduler).  
- Export / import birthdays in **CSV** format for easy backup.  
- Fully typed code with **type hints** and **PEP 8** compliance.  

---  

## Installation  

```bash
# 1. Clone the repository
git clone https://github.com/i252010-ops/Birthday-Reminder-Project.git
cd Birthday-Reminder-Project

# 2. Create and activate a virtual environment (optional but recommended)
python -m venv .venv
# On Windows
.venv\Scripts\activate
# On macOS/Linux
source .venv/bin/activate

# 3. Install required packages
pip install -r requirements.txt
```

> **Note:** The project requires Python 3.9+.

---  

## Usage  

### 1️⃣ Initialise the database  

```bash
python -m birthday_reminder init
```

### 2️⃣ Add a birthday  

```bash
python -m birthday_reminder add \
    --name "Alice Smith" \
    --date "1990-04-15" \
    --email "alice@example.com"
```

### 3️⃣ List all birthdays  

```bash
python -m birthday_reminder list
```

### 4️⃣ Run the reminder daemon  

```bash
python -m birthday_reminder run
```

The daemon checks the database every day at midnight (default) and sends reminders according to the configured lead time.

### 5️⃣ Configure email (once)  

Create a `config.yaml` in the project root:

```yaml
smtp:
  host: smtp.gmail.com
  port: 587
  username: your.email@gmail.com
  password: your_app_password
  use_tls: true
reminder:
  lead_time_days: 1
```

---  

## Contributing  

Contributions are welcome! Please:

1. Fork the repository.  
2. Create a feature branch (`git checkout -b feature/awesome-feature`).  
3. Commit your changes with clear messages.  
4. Open a Pull Request against the `main` branch.  

Make sure to run the test suite before submitting:

```bash
pytest tests/
```

---  

## License  

This project does **not** include a license. By default, all rights are reserved to the author. If you wish to use this code in your own projects, please contact the repository owner for permission.

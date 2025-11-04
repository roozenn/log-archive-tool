project page URL : https://roadmap.sh/projects/log-archive-tool

# 📦 Log Archive Tool

**Log Archive Tool** is a simple command-line utility for archiving log files automatically.  
It adds a timestamp to each archive, compresses it into a `.tar.gz` file, and stores it in a dedicated directory — keeping your system organized without losing important log history.

---

## ✨ Features

- 🔁 Archive entire log directories with a single command  
- 🕒 Automatically timestamped archive names, e.g.:  
  `logs_archive_20251103_143022.tar.gz`  
- 🧾 Records every archive action in `archive_history.log`  
- ⚡ Lightweight, fast, and requires only Bash — no external dependencies

---

## 🚀 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/log-archive-tool.git
   cd log-archive-tool
   ```

2. (Optional) Install globally to run from anywhere:
   ```bash
   sudo cp log-archive /usr/local/bin/
   ```

---

## 🛠️ Usage

Run the tool with:
```bash
log-archive <log-directory>
```

### Example:
```bash
# Archive Nginx logs
log-archive /var/log/nginx

# Archive system logs (requires sudo)
sudo log-archive /var/log
```

> 💡 Make sure the target directory exists and contains log files.

---

## 📂 Output

After running, the tool will generate:
- A `logs_archive/` directory (if it doesn’t exist) — containing the compressed `.tar.gz` archives  
- An `archive_history.log` file — recording when and where each archive was created  

Example directory structure:
```
log-archive-tool/
├── log-archive
├── README.md
├── archive_history.log
└── logs_archive/
    └── logs_archive_20251103_143022.tar.gz
```

---

## 🧭 Tips

- Use `sudo` when archiving system directories like `/var/log`.  
- To automate regular backups, add a cron job:
   ```bash
   # Run every day at 2 AM
   0 2 * * * /usr/local/bin/log-archive /var/log
   ```

---

## 🤝 Contributing

Contributions, suggestions, and feature ideas (like cloud upload or email notifications) are always welcome!  
Feel free to open an issue or submit a pull request.

---

## ⚙️ License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute it as you wish.

---

Built with 💻 for Unix/Linux systems — including WSL.

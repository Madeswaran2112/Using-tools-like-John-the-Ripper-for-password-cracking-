# Using-tools-like-John-the-Ripper-for-password-cracking
## AIM:
To crack password hashes using John the Ripper in Kali Linux.
## REQUIREMENTS:
- **Operating System:** Kali Linux / Ubuntu / Windows (with JtR binaries)
- **Tools:**
    - John the Ripper (Community/Pro version)
    - Hash generating tools (e.g., openssl, unshadow)
- **Test Data:**
    - /etc/shadow file (Linux hashed passwords)
    - Custom password-protected file (ZIP, RAR, etc.)
## ARCHITECTURE DIAGRAM:
```mermaid
flowchart TD
    A[Password Protected File / Hash] --> B[John the Ripper]
    B --> C[Select Attack Mode: Dictionary or Brute Force]
    C --> D[Load Wordlist / Charset Rules]
    D --> E[Password Cracking Process]
    E --> F[Recovered Passwords]
```
## DESIGN STEPS:
### Step 1: Install John the Ripper
```bash
sudo apt update
sudo apt install john -y
```

### Step 2: Prepare Hash File
- Extract hashes (Linux example):
```
unshadow /etc/passwd /etc/shadow > myhashes.txt
```
- For a ZIP file:
```
zip2john secret.zip > ziphash.txt
```
### Step 3: Run John the Ripper
- Dictionary Attack:
```
john --wordlist=/usr/share/wordlists/rockyou.txt myhashes.txt
```
- Brute Force (Incremental Mode):
```
john --incremental myhashes.txt
```
### Step 4: Show Cracked Passwords
```
john --show myhashes.txt
```
## PROGRAM:
1. **Hash Extraction** – Obtain password hashes from system files or encrypted archives.
2. **Attack Mode Selection** – Choose between dictionary, brute force, or hybrid.
3. **Cracking Phase** – John the Ripper runs through candidate passwords.
4. **Password Recovery** – Successfully cracked passwords are displayed.

## Save A file named hello.txt :
## Encrypt with password the file 

![Uploading WhatsApp Image 2025-09-27 at 14.19.38_a67ae208.jpg…]()



![WhatsApp Image 2025-09-27 at 14 19 06_14825556](https://github.com/user-attachments/assets/9739e197-8e39-4014-ad7c-0fe941a1ec42)


## Run john helper:

![IMG-20250927-WA0009](https://github.com/user-attachments/assets/9d033b6e-cd53-47c3-b772-3e4d469adeba)


![IMG-20250927-WA0008](https://github.com/user-attachments/assets/c70b11a7-3804-4868-a281-a4035ae477db)


## In john terminal change the directory 

## Use Zip2john command  
```bash
zip2jhon bello.txt.zip > hash.txt
```

![IMG-20250927-WA0006](https://github.com/user-attachments/assets/bf765645-8872-4285-a6e4-19c94545e6ff)


![IMG-20250927-WA0007](https://github.com/user-attachments/assets/d05a433d-a2a1-49d8-a235-4c6d2cd92832)



## OUTPUT:
Cracked Passwords from Hash File

## RESULT:
The password hashes were successfully cracked using John the Ripper.


# Using-tools-like-John-the-Ripper-for-password-cracking
# Name: Lubindher S
# Reg.No: 212222240056
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

## OUTPUT:
<img width="940" height="934" alt="Screenshot 2025-09-27 133231" src="https://github.com/user-attachments/assets/89509df3-bf6f-4d10-a141-3bb5d34742c0" />

<img width="940" height="1010" alt="Screenshot 2025-09-27 133317" src="https://github.com/user-attachments/assets/67cb189c-7279-476d-831b-89b9ddab5ab4" />

<img width="939" height="994" alt="Screenshot 2025-09-27 133403" src="https://github.com/user-attachments/assets/dd79dd53-0d19-46dd-aab6-4e23383c4066" />

<img width="944" height="1016" alt="Screenshot 2025-09-27 133519" src="https://github.com/user-attachments/assets/a033edfc-188b-46a9-8fbe-7098237139da" />

<img width="931" height="1015" alt="Screenshot 2025-09-27 133647" src="https://github.com/user-attachments/assets/9ee1f0f7-11fe-461f-a1e2-fbce2706ee6d" />

<img width="941" height="1013" alt="Screenshot 2025-09-27 133714" src="https://github.com/user-attachments/assets/953f990e-f54e-4942-a213-6f19412f0f79" />

<img width="942" height="1012" alt="Screenshot 2025-09-27 133824" src="https://github.com/user-attachments/assets/d65134a7-193e-4bd5-9c40-a898745aa8ff" />

<img width="937" height="261" alt="Screenshot 2025-09-27 133935" src="https://github.com/user-attachments/assets/1257022b-f174-487f-adc6-fb4849e1ddc1" />




Cracked Passwords from Hash File

## RESULT:
The password hashes were successfully cracked using John the Ripper.


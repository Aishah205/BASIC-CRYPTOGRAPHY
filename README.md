# Cryptography Lab Setup — Kali Linux & Ubuntu Server
This project demonstrates a **basic cryptography lab** setup using **Kali Linux** and **Ubuntu Server**, focusing on **asymmetric encryption with GPG (GNU Privacy Guard)**. It walks through the process of generating keys, encrypting/decrypting messages, and securely exchanging information.

## Objectives
- Set up a home cybersecurity lab environment.
- Generate GPG key pairs.
- Perform asymmetric encryption using public/private keys.
- Encrypt a file on Kali and decrypt it on Ubuntu.
- Push lab artifacts to GitHub.

## Tools Used
| Tool           | Role                      |
|----------------|---------------------------|
| Kali Linux     | Attacker (Encryption)     |
| Ubuntu Server  | Target (Decryption)       |
| GnuPG (GPG)    | Cryptographic operations  |
| Git & GitHub   | Version control & backup  |

## Setup Instructions
1. GPG Key Generation (Ubuntu Server)
sudo apt install gnupg -y
gpg --full-generate-key

Export public key:
gpg --armor --export ubuntu@example.com > ubuntu_pubkey.asc

2. Import Public Key (Kali Linux)
sudo apt install gnupg -y
gpg --import ubuntu_pubkey.asc

3. Encrypt a Message on Kali
echo "This is a secret message." > secret.txt
gpg --output secret.txt.gpg --encrypt --recipient ubuntu@example.com secret.txt

4. Decrypt on Ubuntu
gpg --output decrypted.txt --decrypt secret.txt.gpg
cat decrypted.txt

5. Push to GitHub
git add .
git commit -m "Initial cryptography lab files"
git push origin main

## Project Structure
crypto-lab/
├── secret.txt.gpg       |   # Encrypted message
├── decrypted.txt        |  # Decrypted message (on Ubuntu)
├── ubuntu_pubkey.asc    |   # Ubuntu's GPG public key
├── README.md            |  # Project documentation

## Possible Extensions

- Add digital signatures to verify authenticity.
- Set up key revocation and trust models.
- Use additional tools like OpenSSL.
- Automate the process with Bash scripts.

## Author
Aishah Adunni Aiyepe  
Cybersecurity Enthusiast  
[GitHub](https://github.com/Aishah205) | [LinkedIn](https://linkedin.com/in/aiyepeayishat)

## License
This project is licensed under the MIT License.

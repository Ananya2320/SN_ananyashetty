# SN_ananyashetty
Problem Statement:  Personal Home Cloud with Secure Multi-Level Access
I propose a novel, practical Personal Home Cloud (PHC) architecture that combines the best “booming” technologies  into a secure, usable, multi-level access system. It’s designed to be private-by-default, easy to use for non-tech people, and resilient.
Software Options:
1. Personal Cloud :
•	Nextcloud :open source, self-hosted cloud drive with sharing, users, roles).
🔹 Can be extended with AI plugins & external storage.
•	ownCloud Infinite Scale : newer, Go-based, scalable.
•	Seafile: efficient file sync + sharing.
•	Syncthing :peer-to-peer sync, lightweight but needs extensions for access levels).
👉 Best choice: Nextcloud → mature, widely used, has plugins, and can integrate AI modules.
Access & security model (how multi-level access works):
1.	File encryption: For each file, PHC generates a random file-symmetric key.

2.	Policy binding (CP-ABE): K_file is encrypted under an attribute policy P (e.g., (owner OR (family AND (age>18))) OR (doctor WHEN appointment=true)) using CP-ABE to produce CT_key. CT_key stored with file metadata. Only devices with attributes satisfying P and correct VC can decrypt CT_key to recover K_file.


3.	Authentication: user signs authentication request with device passkey (FIDO2). PHC verifies the assertion and associates request with a DID.

4.	Attribute verification: user presents a DID VC (or a ZK proof derived from VC) proving required attributes; PHC verifies ZK proof . If verified, KEYSHARE protocol runs (could be a CP-ABE decryption, or threshold decryption involving enclave + MPC shares). 

AI-Powered Unique Solution:

AI for Threat Detection
•	AI scans logs in real-time and looks for abnormal patterns:
o	Too many failed login attempts.
o	Suspicious access times.
•	If detected → system temporarily locks access and notifies owner instantly.
________________________________________
1. AI for Accessibility
•	Built-in voice assistant:
•	 “Show me only vacation photos from last year.”
•	Smart search: AI indexes photos, documents, and videos so users can search by natural language:
________________________________________
2. AI for Recovery & Help
•	If a user loses their device, AI guides them step-by-step:
o	Detects loss patterns (no logins from device for weeks).
o	Suggests recovery through trusted peers.



The PHC diagram shows a secure, layered system where users connect through a protected network to a home cloud that stores, encrypts, and manages files with AI and advanced cryptography, while backups ensure safety and recovery.
<img width="489" height="523" alt="image" src="https://github.com/user-attachments/assets/b18bcaaa-eaac-409a-92ed-ea51f14b235e" />

 

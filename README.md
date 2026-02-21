# BRICKS-HEIST---LAB-SIMULATION-LOG
> Focus: Web Exploitation, IDOR, & Privilege Escalation
> Platform: TryHackMe (THM)
> Date: Feb 21, 2026

---

## [ 01 ] RECONNAISSANCE (ENUMERATION)
Tahap awal untuk memetakan target "Bricks Heist":
* **Port Scanning**: Mengidentifikasi layanan yang berjalan (HTTP, SSH, atau lainnya).
* **Directory Brute-forcing**: Mencari hidden path seperti `/admin`, `/config`, atau API endpoints yang tidak terproteksi.
* **Information Leakage**: Mengecek file `robots.txt` atau komentar di *source code* yang seringkali membocorkan kredensial atau versi software.

---

## [ 02 ] VULNERABILITY EXPLOITATION
Langkah-langkah "pencurian" data (Heist) yang dipelajari:
* **IDOR (Insecure Direct Object Reference)**: Mencoba mengakses data user lain dengan mengganti parameter ID pada URL/API request (misal: `user_id=100` diubah menjadi `user_id=1`).
* **Broken Access Control**: Mengeksploitasi celah di mana user biasa bisa mengakses fitur level Administrator tanpa otentikasi yang benar.
* **Data Exfiltration**: Mengambil informasi sensitif dari database atau file konfigurasi yang terekspos.

---

## [ 03 ] PRIVILEGE ESCALATION (GETTING ROOT)
Setelah mendapatkan akses awal (initial foothold):
* **SUDO Rights**: Mengecek perintah apa yang bisa dijalankan sebagai root tanpa password (`sudo -l`).
* **Exploiting Misconfigurations**: Mencari file dengan SUID bit atau cronjobs yang bisa dimanipulasi untuk mendapatkan shell dengan hak akses tertinggi.



---

## [ 04 ] KEY TAKEAWAYS (LESSONS LEARNED)
1. **Never Trust User Input**: Setiap parameter yang bisa diubah user di browser harus divalidasi ketat di sisi server.
2. **Access Control is Critical**: Pastikan setiap akses ke data sensitif melewati pengecekan otentikasi dan otorisasi.
3. **Log Everything**: Dalam simulasi heist, log audit sangat membantu untuk melihat jejak kaki (footprint) penyerang.

---
*Status: Heist Completed Successfully*
*Researcher: sepkascurty-cpu*

# TryHackMe - Introduction to Offensive Security  
📌 **Platform:** TryHackMe  
🛠 **Tools Used:** Gobuster, Web Exploitation, Linux Terminal  
🎯 **Skills Learned:** Ethical hacking, penetration testing, directory enumeration, exploiting web vulnerabilities  

## 📝 Lab Overview:
This lab introduced the fundamentals of **offensive security**, focusing on **penetration testing techniques** used by ethical hackers. The goal was to simulate an attack on a **fake online banking application** by discovering hidden directories, accessing restricted areas, and exploiting vulnerabilities to manipulate transactions.

## 🔍 Attack Process:
1. **Directory Enumeration with Gobuster:**  
   - Ran Gobuster to scan for **hidden web directories**.  
   - Discovered `/bank-transfer` endpoint, which was **not publicly accessible**.  
   - **Command used:**
     ```
     gobuster dir -u http://fakebank.thm -w /usr/share/wordlists/dirb/common.txt
     ```
   - **Output:**
     ```
     /admin
     /bank-transfer
     /login
     ```

2. **Exploiting the Bank Application:**  
   - Navigated to `/bank-transfer` and analyzed its **functionality & security flaws**.  
   - Found that **transaction security was weak**, allowing unauthorized transfers.  
   - Successfully **transferred funds** between accounts without proper authentication.  

## 🔑 Key Takeaways:
- **Gobuster is an essential tool** for discovering hidden files and directories that could expose vulnerabilities.  
- Attackers often exploit **poorly secured admin panels** to gain access.  
- **Proper authentication & access control** are crucial for protecting web applications.  
- Understanding **offensive security techniques helps cybersecurity analysts** strengthen defenses.  

## ⚠️ Challenges Faced & How I Solved Them:
- **Initial 403 Forbidden Error:** While attempting to access `/admin`, I encountered a **403 Forbidden response**.  
  - **Solution:** Changed the **User-Agent** in the request header to bypass restrictions.
- **No Direct Admin Panel Access:** The `/admin` panel wasn’t listed but was identified through wordlist-based enumeration.  
  - **Solution:** Explored **default credentials** and **common misconfigurations** to gain further access.  

📸 **Screenshot:**  
![Gobuster FakeBank Attack](https://github.com/MoyoJacob01/Cybersecurity-Projects-/blob/main/image.png?raw=true))

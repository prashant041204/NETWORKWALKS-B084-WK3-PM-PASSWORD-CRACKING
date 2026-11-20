# WEEK 3 – CYBERSECURITY INTERNSHIP PROJECTS

**Domain:** Cybersecurity & Ethical Hacking  
**Platform:** Kali Linux  
**Training Provider:** Networkwalks Academy  
**Project Type:** Practical Cybersecurity Labs

---

# 1. Project Overview

This repository contains the implementation and documentation of four cybersecurity projects completed as part of Week 3 of the Cybersecurity Internship.

The projects cover password security testing, password recovery, AI-assisted cybersecurity automation and web application security testing.

The main objective is to gain practical experience with commonly used cybersecurity tools and understand how security testing techniques are applied in authorised laboratory environments.

## 2. Projects Included

| Project | Name | Category |
|---|---|---|
| W3-PM1 | Password Cracking with John the Ripper | Mandatory |
| W3-PM2 | Password Cracking with Networkwalks Tools | Mandatory |
| W3-OPTIONAL1 | AI-Assisted JTR Password Cracking | Optional |
| W3-OPTIONAL2 | Mediroza Hospital Patient Portal Hacking | Optional |

---

# 3. Technologies and Tools Used

| Tool / Technology | Purpose |
|---|---|
| Kali Linux | Cybersecurity testing environment |
| John the Ripper | Password recovery |
| Johnny GUI | Graphical interface for John |
| pdf2john | PDF hash extraction |
| Claude Desktop | AI assistant |
| HexStrike MCP | AI and cybersecurity tool integration |
| Python 3 | Runtime environment |
| Git | Repository management |
| Networkwalks Hash Calculator | PDF hash extraction |
| Networkwalks Password Cracker | Password recovery |
| Web Browser | Accessing online lab tools |

---

# PROJECT 1 – PASSWORD CRACKING WITH JOHN THE RIPPER

## 4. Introduction

John the Ripper is a password security auditing and recovery tool used to identify weak passwords.

It supports multiple password hash formats and can perform dictionary-based password recovery.

In this practical, John the Ripper was used to recover the password of an assigned password-protected PDF using a supplied dictionary.

## 5. Objectives

- Understand password-protected PDF files.
- Learn PDF hash extraction.
- Install and configure John the Ripper.
- Understand dictionary-based password recovery.
- Verify the recovered password.

## 6. Environment

**Operating System:** Kali Linux  
**Tool:** John the Ripper 1.9.0 Jumbo  
**Hash Extraction:** pdf2john  
**Dictionary:** JTR_default_password.txt

## 7. Installation and Configuration

Check John installation:

```bash
john --help
```

Locate the executable:

```bash
find /usr -name 'john*' 2>/dev/null
```

Check PDF hash extraction utility:

```bash
find /usr /opt -name 'pdf2john*' 2>/dev/null
```

## 8. Practical Implementation

Navigate to the Documents directory:

```bash
cd /home/kali/Documents
```

Create the output directory:

```bash
mkdir -p Week3_Work/Hashes
```

Extract the hash from the assigned lab PDF:

```bash
pdf2john "My Locked PDF1.pdf" > Week3_Work/Hashes/hash.txt
```

Check the extracted hash file:

```bash
ls -lh Week3_Work/Hashes/hash.txt
```

Verify the supplied dictionary:

```bash
ls -lh JTR_default_password.txt
```

The practical involved using the supplied dictionary to test password candidates against the extracted PDF hash.

## 9. Result

**Status: Successfully Completed**

The password was recovered successfully.

**Recovered password:**

```text
good-luck
```

John the Ripper displayed:

```text
1 password hash cracked, 0 left
```

This confirmed that the assigned PDF password was successfully recovered.

## 10. Learning Outcomes

- Learned how PDF password hashes are extracted.
- Understood dictionary-based password recovery.
- Gained practical experience with John the Ripper.
- Learned how to verify password recovery results.
- Understood the importance of strong passwords.

---

# PROJECT 2 – PASSWORD CRACKING WITH NETWORKWALKS TOOLS

## 11. Introduction

This project demonstrates password recovery using two browser-based tools developed by Networkwalks.

The practical uses a Hash Calculator to extract the PDF hash and a Password Cracker to recover the original password.

No additional software installation is required for these online tools.

## 12. Objectives

- Understand PDF hash extraction.
- Learn how online password recovery tools work.
- Generate a PDF hash.
- Use the Networkwalks Password Cracker.
- Verify the recovered password.

## 13. Tools Used

**Hash Calculator:**

https://networkwalks.com/hash-calculator/

**Password Cracker:**

https://networkwalks.com/password-cracker/

**Operating System:** Kali Linux

## 14. Practical Implementation

### Step 1: Identify the assigned PDF

The assigned file was:

```text
My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf
```

### Step 2: Open Hash Calculator

Navigate to:

https://networkwalks.com/hash-calculator/

Upload the assigned password-protected PDF.

### Step 3: Generate the hash

The calculator processes the PDF and generates its hash.

The extracted hash begins with:

```text
$pdf$
```

Copy the complete generated hash.

### Step 4: Open Password Cracker

Navigate to:

https://networkwalks.com/password-cracker/

### Step 5: Perform password recovery

Paste the complete extracted hash into the Password Cracker and start the recovery process.

### Step 6: Verify the result

Use the recovered password to open the assigned PDF.

## 15. Result

**Status: Successfully Completed**

The recovered password was:

```text
password1
```

The assigned PDF was successfully opened using the recovered password.

## 16. Learning Outcomes

- Learned how online PDF hash calculators work.
- Understood the relationship between password hashes and password recovery.
- Gained experience with Networkwalks cybersecurity tools.
- Learned how to verify recovered passwords.

---

# PROJECT 3 – AI-ASSISTED PASSWORD CRACKING WITH CLAUDE DESKTOP AND HEXSTRIKE MCP

## 17. Introduction

This optional project demonstrates the integration of Claude Desktop with the HexStrike MCP Server in Kali Linux.

The Model Context Protocol (MCP) enables AI applications to communicate with external tools through configured integrations.

The practical combines AI-assisted interaction with John the Ripper for password recovery in an authorised laboratory environment.

## 18. Objectives

- Install Claude Desktop.
- Download and configure HexStrike AI.
- Create a Python virtual environment.
- Install project dependencies.
- Configure the MCP server.
- Establish communication between Claude Desktop and HexStrike.
- Perform the assigned PDF password recovery exercise.

## 19. Tools and Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Claude Desktop | AI interface |
| HexStrike AI | MCP integration |
| Python 3 | Runtime |
| Git | Repository cloning |
| John the Ripper | Password recovery |
| RockYou | Dictionary |

## 20. Installation and Configuration

### Step 1: Install Claude Desktop

The lab manual references the following Debian community project:

https://github.com/aaddrick/claude-desktop-debian

Add the repository key:

```bash
curl -fsSL https://pkg.claude-desktop-debian.dev/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/claude-desktop.gpg
```

Add the repository:

```bash
echo "deb [signed-by=/usr/share/keyrings/claude-desktop.gpg arch=amd64,arm64] https://pkg.claude-desktop-debian.dev stable main" | sudo tee /etc/apt/sources.list.d/claude-desktop.list
```

Update packages:

```bash
sudo apt update
```

Install:

```bash
sudo apt install claude-desktop
```

Open Claude Desktop and sign in.

### Step 2: Download HexStrike AI

Repository:

https://github.com/0x4m4/hexstrike-ai

Clone:

```bash
git clone https://github.com/0x4m4/hexstrike-ai.git
```

Navigate:

```bash
cd hexstrike-ai
```

### Step 3: Create Python Virtual Environment

```bash
python3 -m venv hexstrike-env
```

Activate:

```bash
source hexstrike-env/bin/activate
```

### Step 4: Install Dependencies

```bash
pip3 install -r requirements.txt
```

Verify:

```bash
which python
```

### Step 5: Start HexStrike Server

```bash
cd ~/hexstrike-ai
```

```bash
source hexstrike-env/bin/activate
```

```bash
python3 hexstrike_server.py
```

Keep the server running.

### Step 6: Configure Claude Desktop MCP

Add the following configuration to the Claude Desktop MCP configuration file:

```json
{
  "mcpServers": {
    "hexstrike-ai": {
      "command": "/home/kali/hexstrike-ai/hexstrike-env/bin/python",
      "args": [
        "/home/kali/hexstrike-ai/hexstrike_mcp.py",
        "--server",
        "http://localhost:8888"
      ]
    }
  }
}
```

Save the configuration and restart Claude Desktop.

### Step 7: Verify Integration

- Open Claude Desktop.
- Check the MCP server connection.
- Verify that HexStrike tools are available.
- Check the server terminal for errors.

## 21. AI-Assisted JTR Practical

The optional lab manual specifies the following target:

```text
hash3.networkwalks_flag1.pdf
```

The manual instructs the user to:

1. Copy the supplied target PDF to the Kali Desktop.
2. Open Claude Desktop.
3. Ask Claude to check whether John the Ripper is installed through HexStrike MCP.
4. Ask Claude to calculate the target PDF hash.
5. Request the authorised lab password-recovery operation using the RockYou dictionary.
6. Record and verify the result.

Example prompts from the lab:

```text
Check if John the Ripper is installed in this HexStrike MCP and show me its version.
```

```text
Please calculate the hash value of this PDF file:
/home/kali/Desktop/hash3.networkwalks_flag1.pdf
```

```text
Please use JTR tool in this HexStrike MCP server to recover the password of this PDF file. Use the rockyou.txt wordlist dictionary.
```

## 22. Expected Result

The expected outcome is successful communication between Claude Desktop and HexStrike MCP, followed by the assigned PDF password-recovery exercise.

**Completion status:** Setup and practical results should be recorded after actual MCP connection verification and completion of the supplied PDF exercise.

Note: The target file `hash3.networkwalks_flag1.pdf` was not included in the uploaded ZIP. It must be obtained from the authorised lab attachment before completing this exercise.

## 23. Learning Outcomes

- Understood Model Context Protocol.
- Learned how AI applications interact with external tools.
- Gained experience configuring MCP servers.
- Learned Python virtual environment management.
- Explored AI-assisted cybersecurity workflows.

---

# PROJECT 4 – MEDIROZA HOSPITAL PATIENT PORTAL HACKING

## 24. Introduction

Mediroza Hospital Patient Portal Hacking is listed as the second optional project in the Week 3 project overview.

The project falls under the web application security testing category.

The purpose is to understand how a hospital patient portal can be evaluated for security weaknesses in an authorised training environment.

**Important:** The uploaded Week 3 ZIP contains the project title but does not include a separate practical manual, target URL, credentials, or testing instructions for this module.

Therefore, the following is a proposed documentation and testing framework, not a claim that these activities were performed or prescribed by the training provider.

## 25. Objectives

- Understand hospital patient portal functionality.
- Learn the fundamentals of web application security.
- Identify potential security weaknesses in an authorised test environment.
- Understand authentication and access control.
- Examine session management.
- Document security observations.
- Prepare recommendations for improving application security.

## 26. Proposed Tools

The following tools may be considered if permitted by the lab instructions:

| Tool | Purpose |
|---|---|
| Kali Linux | Testing environment |
| Firefox | Browser-based testing |
| Burp Suite Community | HTTP request inspection |
| OWASP ZAP | Web application security assessment |
| Nmap | Authorised service discovery |
| Developer Tools | Browser-side inspection |

Tool selection and testing scope must be confirmed using the official project instructions.

## 27. Proposed Testing Areas

### 1. Authentication Testing

Understand how users log in and how authentication is handled.

### 2. Session Management

Review session handling and session security in the authorised environment.

### 3. Access Control

Examine whether users can access only the information and functionality permitted by their assigned roles.

### 4. Input Validation

Review how the application validates user-supplied data.

### 5. Security Configuration

Review security-related headers, HTTPS usage and error handling.

### 6. Reporting

Document observations, evidence, severity and recommendations.

## 28. Security and Privacy Considerations

Hospital portals may contain highly sensitive patient information.

All testing must be conducted only on the training provider's explicitly authorised target.

- Never access real patient records.
- Do not test public hospital systems without written permission.
- Do not download or disclose private information.
- Do not modify or delete data.
- Use only the assigned test accounts.
- Follow the lab scope and rules.

## 29. Result

**Completion status: Pending official lab instructions and authorised target access.**

The actual testing methodology, findings and screenshots should be added after receiving the separate practical manual.

## 30. Expected Learning Outcomes

- Understanding web application security.
- Learning authentication and session management concepts.
- Understanding access control.
- Learning vulnerability documentation.
- Developing security assessment and reporting skills.

---

# 31. Overall Project Summary

| Project | Result |
|---|---|
| W3-PM1 – John the Ripper | Completed |
| W3-PM2 – Networkwalks Tools | Completed |
| W3-OPTIONAL1 – AI + HexStrike MCP | In progress / verify MCP and lab result |
| W3-OPTIONAL2 – Mediroza Portal | Awaiting lab instructions |

# 32. Overall Conclusion

The Week 3 internship projects provide practical exposure to password security, dictionary-based password recovery, AI-assisted cybersecurity integration and web application security assessment.

The mandatory projects provided hands-on experience with John the Ripper and Networkwalks password recovery tools.

The first optional project introduces the integration of Claude Desktop with HexStrike MCP to explore AI-assisted cybersecurity workflows.

The second optional project introduces the concepts of web application security testing through a hospital patient portal scenario.

Together, these projects help develop practical knowledge of Linux, cybersecurity tools, password security, AI integration and security assessment documentation.

# 33. References

1. Networkwalks Academy – Week 3 Project Overview.
2. Networkwalks Academy – Password Cracking with JTR.
3. Networkwalks Academy – Password Cracking with Networkwalks Tools.
4. Networkwalks Academy – How to Setup HexStrike MCP with Claude.
5. Networkwalks Academy – Optional JTR Password Cracking Lab (AI Version).
6. John the Ripper: https://www.openwall.com/john/
7. HexStrike AI: https://github.com/0x4m4/hexstrike-ai
8. Claude Desktop Debian Community Project: https://github.com/aaddrick/claude-desktop-debian
9. Model Context Protocol: https://modelcontextprotocol.io/
10. Networkwalks: https://www.networkwalks.com/

---

**Repository:** Week 3 Cybersecurity Internship  
**Training Provider:** Networkwalks Academy  
**Operating Environment:** Kali Linux  
**Documentation:** README.md

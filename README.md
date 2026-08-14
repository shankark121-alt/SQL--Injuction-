# INTRODUCTION

SQL Injection (SQLi) is a web application vulnerability that occurs when user-supplied input is directly incorporated into an 
SQL query without proper validation or parameterization.

An attacker can manipulate the SQL query to:
Bypass application logic
Retrieve database information
Enumerate databases/tables
Extract sensitive records
Modify or delete data, depending on application privileges

In DVWA, SQL Injection can be practiced at different security levels:

Low
Medium
High
Impossible

# LAB ENVIORNMENT

| Component | Details |
|-----------|---------|
| Attacker Machine | Kali Linux |
| Target Application | DVWA (Damn Vulnerable Web Application) |
| Web Server | Apache |
| Database | MySQL / MariaDB |
| Programming Language | PHP |
| Browser | Firefox / Google Chrome |
| Vulnerabilities | SQL Injection & Blind SQL Injection |
| Security Levels | Low, Medium, High |
| Tools Used | Web Browser, Burp Suite (Optional) |
| Network | Localhost / Isolated Virtual Lab |
| Purpose | Security testing and vulnerability analysis |

# PRACTICAL STEPS FOR SQL INJUCTION

Start DVWA by login 192.168.190.135/DVWA

Login by using Username and Password

Set: DVWA security Low

Click SQL injuction
<img width="1234" height="651" alt="image" src="https://github.com/user-attachments/assets/eb6eb234-14b5-4a71-881a-2d3d21157860" />

 # SQL Injection — Low Level
   
   At Low level, DVWA provides a User ID input.

   First test a normal value: 1
  <img width="1234" height="648" alt="image" src="https://github.com/user-attachments/assets/6775f256-91e6-484d-9c53-dfb4929aee7f" />

# Authentication/logic bypass test

  <img width="910" height="569" alt="image" src="https://github.com/user-attachments/assets/9a577441-907f-4b96-b511-22e0e8213b50" />
  
  Another commonly used from
  <img width="900" height="556" alt="image" src="https://github.com/user-attachments/assets/e3a6dfbe-2a2e-4627-946a-869cb1367258" />
  
# Determine the number of columns

 <img width="908" height="553" alt="image" src="https://github.com/user-attachments/assets/b1e45d16-30a7-405a-8364-d190ecf51107" />

# 4. UNION-Based SQL Injection

Once you know the column count, you can test UNION.  

For example, if two columns are returned:

<img width="898" height="557" alt="image" src="https://github.com/user-attachments/assets/fac7f27b-3bee-407c-bc28-aad55c2b2596" />

Then test database information:

<img width="904" height="560" alt="image" src="https://github.com/user-attachments/assets/2a9c677e-2dcb-4305-820a-65a9d4567257" />

This can reveal:

Current database
MySQL version

<img width="910" height="557" alt="image" src="https://github.com/user-attachments/assets/a08c11bf-a1eb-4bb9-ac92-37445e11700c" />

# SQL Injection – Medium Level

Change:

DVWA Security → Medium

Go Back and on SQL Injuction

Medium level introduces additional input handling/filtering. The DVWA project notes that the SQL Injection and Blind 
SQL Injection input handling was changed to POST for the medium-level challenge.

# Step 1 – Test Normal Input

Enter:

1

<img width="875" height="621" alt="image" src="https://github.com/user-attachments/assets/7dc95330-eb2a-4a63-9d89-4c914ab1fb6e" />

Step 2 – Test Boolean Injection

Try: 






  





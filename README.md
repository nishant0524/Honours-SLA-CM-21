# Understanding SQL Injection: Methods, Impact, and Prevention
**Author:** Nishant Patil  
**Category:** Ethical Hacking Self-Learning Activity-1

## 1. Introduction to SQL Injection (SQLi)
In the world of cybersecurity, SQL Injection (SQLi) remains one of the most prevalent and dangerous vulnerabilities[cite: 1]. At its core, SQLi is a type of attack where an attacker inserts malicious SQL code into a query through an input field[cite: 1]. This "injection" tricks the database into executing commands that the developer never intended, such as revealing private user data or bypassing authentication entirely[cite: 1].

## 2. How the Attack Works (The Beginner's View)
Imagine a website has a login form. When you enter your credentials, the backend code usually looks like this:
`SELECT * FROM users WHERE username = 'input_user' AND password = 'input_password';`

An attacker doesn't enter a real username. Instead, they enter: `' OR '1'='1`.
The query becomes:
`SELECT * FROM users WHERE username = '' OR '1'='1' AND password = '';`

Because `'1'='1'` is always true, the database grants access without a valid password. This simple logic flaw is the foundation of most SQLi attacks[cite: 1].

## 3. Case Study: The TalkTalk Data Breach (2015)
One of the most famous examples of SQLi occurred in 2015 when the UK-based telecom giant, **TalkTalk**, was hacked.
*   **The Flaw:** The attackers exploited a basic SQL injection vulnerability on a legacy webpage that TalkTalk had forgotten to secure[cite: 1].
*   **The Impact:** The personal data of over 150,000 customers, including names, addresses, and partial bank details, was stolen.
*   **The Consequence:** TalkTalk was fined £400,000, and the total cost of the breach exceeded £77 million. This case proves that even simple vulnerabilities can lead to catastrophic business failure.

## 4. Common Types of SQL Injection
*   **In-band SQLi (Classic):** The attacker uses the same communication channel to launch the attack and gather results (e.g., the data appears right on the screen).
*   **Inferential (Blind) SQLi:** The attacker doesn't see the data on the screen but "asks" the database true/false questions based on how the page loads or how long it takes to respond.
*   **Out-of-band SQLi:** The attacker makes the database send the stolen data to a server they control.

## 5. Prevention: The Role of an Ethical Hacker
As ethical hackers, our goal is to identify these flaws before malicious actors do. Prevention strategies include:
*   **Prepared Statements (with Parameterized Queries):** This ensures the database treats user input as data only, never as executable code.
*   **Input Validation:** Only allowing expected characters (e.g., a zip code field should only allow numbers).
*   **Principle of Least Privilege:** Ensuring the database user account only has the permissions it absolutely needs (e.g., it shouldn't be able to delete tables).

## 6. Conclusion
SQL Injection is a fundamental topic in the Ethical Hacking syllabus. By understanding how to exploit it, we learn the critical importance of secure coding and proactive scanning. 

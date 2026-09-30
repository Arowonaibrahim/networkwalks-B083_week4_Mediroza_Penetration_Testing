**WEEK 4 — MEDIROZA GENERAL HOSPITAL PENETRATION TEST**


**Penetration Testing & Vulnerability Assessment**

Program: Cybersecurity

Batch: B083 – Networkwalks

Week: 04

Project: Mediroza General Hospital Penetration Test

Target: https://medirozahospital.com

Testing Type: Black-Box Penetration Test

Duration: 5 Days  

 **Disclaimer**: This project was performed in a controlled environment and the target was authorized for security testing by Networkwalks. The techniques used must not be applied to systems without explicit permission.     

**EXECUTIVE SUMMARY**
    
During Week 4 of my cybersecurity internship training with Networkwalks, I worked on a black-box penetration-testing project for Mediroza General Hospital.

The main objective was to assess the security of the authorized web application, identify weaknesses, demonstrate their impact, and document the findings professionally.

One of the major weaknesses identified during the assessment was SQL Injection in the application's authentication mechanism.

During testing, I observed that the login system responded differently depending on whether the username or password was incorrect. This behavior helped me analyze how the application processed user input.

The project also involved retrieving protected files, analyzing their security, working with password/hash-related tools, and investigating further information exposed by the application.

The assessment followed the scope provided by Networkwalks and was performed only against the authorized target.

**SCOPE AND METHODOLOGY**
   
  **Scope**
  
The target for the assessment was:

Mediroza General Hospital

Target: https://medirozahospital.com

The engagement was a full black-box penetration test. The objective was to identify vulnerabilities, demonstrate their impact, and document the findings.

The testing rules included:

- Testing was limited to the target domain.
- No social engineering was performed.
- No denial-of-service testing was performed.
- Testing was performed only within the approved scope.

**TOOLS USED**

The following tools were used during the project:

- Kali Linux — cybersecurity testing environment
- Browser/Web Application — used to interact with the target application
- Hash Calculator — used for hash analysis and password-related activities
- Networkwalks Password Cracker — used during the authorized password-cracking stage
- SQL Injection techniques — used to assess the application's input validation and authentication mechanism
  
The exact tools and techniques were selected based on the requirements of each milestone.

**MILESTONE 1 - INITIAL ACCESS**

  **Reconnaissance**
  
I started by interacting with the authorized Mediroza General Hospital web application and examining the available pages and authentication functionality.
The objective was to identify possible entry points that could be tested within the approved scope.
The project instructions specifically required reconnaissance, identification of exposed entry points, analysis of authentication behavior, and examination of how the application handled user input.

   **Authentication Testing**

During the login testing, I noticed that the application provided different responses depending on the incorrect information supplied.
For example, when one part of the login credentials was incorrect, the application could indicate whether the username or password was incorrect.
This behavior provided useful information during the assessment because it revealed details about how the authentication process handled user input.

   **SQL Injection Vulnerability**
   
During further testing, I identified that the login functionality was vulnerable to SQL Injection.
The application did not properly handle certain user inputs before processing them against the database.
This showed that user-supplied input could potentially influence the database query used by the authentication system.
The vulnerability was tested only against the authorized training target.

**Security Impact**

A SQL Injection vulnerability in an authentication mechanism can have serious consequences because an attacker may potentially manipulate database queries and bypass intended application controls.
Depending on the application's database permissions and implementation, SQL Injection can potentially lead to unauthorized access or exposure of sensitive information.

**PROOF OF EXPLOITATION**

The SQL Injection finding was verified through controlled testing against the authorized target.

**Observation**

The login application processed user input in a way that allowed SQL Injection testing to affect the authentication process.

**Result**

The vulnerability provided a path toward bypassing the normal authentication mechanism and gaining access to a restricted area of the application.

**Evidence**

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_00_02" src="https://github.com/user-attachments/assets/e3ad73fc-5cde-4c2c-8970-c84a30a32609" />

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_01_01" src="https://github.com/user-attachments/assets/84b8c71e-55af-40f4-9ed0-fd5a7555c055" />

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_01_28" src="https://github.com/user-attachments/assets/7a95e678-a0d8-4548-9c79-8935634bdf37" />


**MILESTONE 2 — DATA EXTRACTION AND FILE SECURITY**

After gaining access to the restricted area, the next stage involved locating the confidential patient PDF laboratory reports specified in the project instructions.
The project required the retrieval of three confidential patient PDF laboratory reports.     

**Retrieved Files**

<img width="643" height="507" alt="Screenshot 2026-09-30 121929" src="https://github.com/user-attachments/assets/d26bccc1-dc83-48d9-adf4-bca5677508da" />

The retrieved files were then examined as part of the next stage of the assessment.

**PASSWORD / HASH ANALYSIS**

The retrieved files required further analysis as part of the project.
I used Hash Calculator to work with the relevant hash information and Networkwalks Password Cracker as part of the authorized password-recovery exercise.
The objective was to understand how the protected information could be recovered and to demonstrate the security impact of the discovered weakness.
The project instructions specifically required the encryption on all three retrieved files to be analyzed and appropriate tools to be selected for recovering their contents.    

**Tools Used**

- Hash Calculator
- Networkwalks Password Cracker
- Kali Linux
  
**Results**

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_08_43" src="https://github.com/user-attachments/assets/cde3ca50-8f21-4b53-9bc3-27725805c436" />

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_10_41" src="https://github.com/user-attachments/assets/794f33b9-914d-4a83-a011-9158626e2de7" />

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_50_46" src="https://github.com/user-attachments/assets/771638fb-7f30-4a64-b540-0435d4d79522" />

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_08_58" src="https://github.com/user-attachments/assets/dfe87f3a-a82b-46bc-b52f-4a71aab33e41" />

<img width="1600" height="775" alt="VirtualBox_kali-linux-2026 2-virtualbox-amd64_30_09_2026_09_10_41" src="https://github.com/user-attachments/assets/06e2fd8f-7856-44ed-a91d-64cfb042d1a4" />

**MILESTONE 3 — CRITICAL DATA EXPOSURE**

The third stage involved investigating the information obtained during the previous stages and looking beyond the obvious content.
The project required identifying further sensitive information exposed by the client's server, including:

- Hospital employee salaries
- Hospital shareholder details
      
During this stage, I analyzed the information available from the recovered data and investigated the additional exposure.

Employee Salary Information

Number of employees identified: 

| Name | Job Title | Department | Monthly Salary |
|---|---|---|---:|
| Dr. Rajesh Naidoo | Chief Pathologist | Diagnostics Lab | R138,000 |
| Sarah Botha | Chief Financial Officer | Finance | R152,000 |
| Dr. Johan van der Merwe | Medical Director | Management | R160,000 |
| Dr. Anita Naicker | Consultant Cardiologist | Cardiology | R132,000 |
| Dr. Ahmed Kara | Consultant Physician | Internal Medicine | R128,000 |
| Dr. Yusuf Cassim | Senior Registrar | Emergency & Trauma | R74,000 |
| Michael Roberts | HR Director | Human Resources | R96,000 |
| Susan Pretorius | HR Officer | Human Resources | R32,000 |
| Jameel Malik | IT Systems Administrator | IT | R58,000 |
| Thabo Molefe | Network Engineer | IT | R46,000 |
| Nomvula Khumalo | Registered Nurse | Emergency & Trauma | R34,000 |
| Lerato Mokoena | Registered Nurse | Pediatrics | R33,000 |
| Bongani Ndlovu | Registered Nurse | Cardiology | R35,000 |
| Zanele Mahlangu | Nursing Sister | Theatre | R42,000 |
| Kagiso Sithole | Pharmacist | Pharmacy | R61,000 |
| Naledi Zulu | Pharmacy Assistant | Pharmacy | R26,000 |
| Themba Nkosi | Radiographer | Radiology | R44,000 |
| Palesa Radebe | Radiographer | Radiology | R43,000 |
| Deepak Pillay | Lab Technologist | Diagnostics Lab | R41,000 |
| Kavitha Govender | Lab Technician | Diagnostics Lab | R35,000 |
| Dr. Suresh Moodley | Consultant Radiologist | Radiology | R130,000 |
| Dr. Fatima Patel | Pediatrician | Pediatrics | R118,000 |
| Nisha Singh | Physiotherapist | Rehabilitation | R48,000 |
| Dr. Vikram Chetty | Anaesthetist | Theatre | R135,000 |
| David Smith | Facilities Manager | Operations | R52,000 |
| Karen O'Connor | Billing Administrator | Finance | R29,000 |
| James Wilson | Security Supervisor | Operations | R27,000 |
| Linda Fourie | Receptionist | Front Office | R19,000 |
| Peter van Wyk | Procurement Officer | Supply Chain | R38,000 |
| Andile Mbeki | Ward Clerk | Administration | R21,000 |

The salary information discovered during the assessment was documented separately to avoid unnecessarily exposing sensitive information in the public repository.

Shareholder Information

The shareholder information identified during the assessment was also documented as part of the project evidence.

Shareholder details: 

| Shareholder Name | Share Percentage | Share Class |
|---|---:|---|
| Dr. Rajesh Naidoo | 18% | Ordinary |
| Cedar Health Holdings (Pty) Ltd | 15% | Ordinary |
| Dr. Johan van der Merwe | 12% | Ordinary |
| Reddy Family Trust | 11% | Ordinary |
| Thabo Molefe | 10% | Ordinary |
| Sarah Botha | 9% | Ordinary |
| Dr. Ahmed Kara | 8% | Preferential |
| Naledi Zulu | 7% | Ordinary |
| Michael Roberts | 6% | Ordinary |
| Dr. Vikram Chetty | 4% | Preferential |

**RISK ANALYSIS / IMPACT**

   **SQL Injection**

- Observation: The authentication functionality was vulnerable to SQL Injection.
- Impact: An attacker may potentially manipulate database queries and bypass application authentication.
- Risk Level: Critical
  
  **Authentication Information Disclosure**

- Observation: The login system provided different responses for incorrect usernames and passwords.
- Impact: This may help an attacker determine whether a username exists.
- Risk Level: Medium
  
  **Confidential Patient Data Exposure**
  
- Observation: Confidential patient PDF laboratory reports could be accessed after exploiting the application.
- Impact: Unauthorized access to patient information represents a serious confidentiality risk.
- Risk Level: Critical

  **Weak Protection of Retrieved Files**

- Observation: The retrieved files required password/encryption analysis and password recovery.
- Impact: If file protection is weak, confidential information may be exposed after unauthorized access to the files.
- Risk Level: High
  
  **Sensitive Business Information Exposure**

- Observation: Employee salary and shareholder information was exposed during the assessment.
- Impact: Unauthorized disclosure of employee and business information could create privacy, financial, and reputational risks.
- Risk Level: High
  
These risk ratings describe the security impact observed during the authorized training exercise.

**RECOMMENDATIONS AND REMEDIATIONS**

**Prevent SQL Injection**

The application should use parameterized queries/prepared statements instead of directly inserting user input into SQL queries.
Input validation should also be implemented as an additional security control.

**Improve Authentication Responses**

The login system should avoid revealing whether the username or password is incorrect.
A generic authentication message should be used to reduce username enumeration.

**Protect Patient Information**

Confidential patient reports should only be accessible to properly authenticated and authorized users.
Access controls should be reviewed and tested regularly.

**Strengthen File Protection**

Sensitive files should use strong encryption and appropriate password protection.
Passwords used to protect sensitive files should be strong and unique.

**Protect Sensitive Database Information**

Employee salary and shareholder information should not be unnecessarily exposed through the web application.
Database permissions should follow the principle of least privilege.

**Secure Database Accounts**

The web application should use a database account with only the permissions it actually needs.
This can reduce the potential impact of a successful SQL Injection attack.

**Conduct Regular Security Testing**

Regular penetration testing and vulnerability assessments should be performed to identify weaknesses before they can be exploited.

**ETHICAL AND SECURITY CONSIDERATIONS**

This assessment was performed as part of an **authorized cybersecurity training project.**

Networkwalks explicitly authorized testing of the Mediroza General Hospital training target and restricted the assessment to the agreed scope.

The SQL Injection, password-cracking, and data-access activities were performed strictly for educational and security-assessment purposes.
No testing was performed outside the authorized target, and no denial-of-service or social-engineering activities were carried out.
This project reinforced the importance of responsible vulnerability disclosure, authorization, scope control, and ethical penetration testing.

**WHAT I LEARNED**

Week 4 was one of the most challenging practical exercises I have completed so far, but it gave me valuable hands-on experience.

**I learned:**

- How to approach a black-box penetration test.
- How to analyze a web application's authentication mechanism.
- How SQL Injection vulnerabilities can occur.
- How improper input handling can affect database queries.
- How to identify and document proof of exploitation.
- How to analyze protected files.
- How to use Hash Calculator for hash-related analysis.
- How to use the Networkwalks Password Cracker.
- How to investigate sensitive information exposure.
- How to perform risk analysis.
- How to provide practical security recommendations.
- How to document penetration-testing findings professionally.
- How important authorization and scope are during security testing.
- How to think about security from both an attacker and defender perspective.
- How to improve my penetration-testing report writing skills.

**CONCLUSION**

Week 4 gave me practical experience in web application penetration testing, SQL Injection, data extraction, password/hash analysis, and security reporting.
The project required me to work through different stages, beginning with identifying an entry point and analyzing the application's authentication mechanism.
I was able to identify a SQL Injection vulnerability and use the authorized testing environment to demonstrate its potential impact.
The project also involved analyzing protected files and investigating further exposure of sensitive information, including employee salary and shareholder information, as required by the assessment.     
Overall, this project improved my technical skills, problem-solving ability, vulnerability analysis, risk assessment, and professional report-writing skills.
Most importantly, I learned that successful penetration testing is not only about finding vulnerabilities but also about understanding their impact, documenting clear evidence, and providing practical recommendations for remediation. 

**AUTHOR**

NAME: Arowona Ibrahim Olanrewaju

linkedIn: https://www.linkedin.com/in/ibrahim-arowona-26709140a?utm_source=share_via&utm_content=profile&utm_medium=member_android

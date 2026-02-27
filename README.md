# Rimon Hamo – Computer Science Portfolio

## CS-305: Software Security  
Feb-27-2026

### Module 8 Journal – Final Course Artifact

**Artifact Submitted**  
- [Artemis Financial Practices for Secure Software Report.pdf](Artemis-Financial-Practices-for-Secure-Software-Report.pdf)  

(This document demonstrates my ability to refactor code securely, implement cryptographic support, enable HTTPS, and apply industry-standard security testing protocols.)

---

### Course Reflections

**Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?**  
Artemis Financial is a financial services company that provides investment and retirement planning to its clients. The company wanted to modernize its existing web application to meet today’s security standards. Their primary concern was protecting sensitive client financial information from tampering and man-in-the-middle attacks. They specifically asked for a secure file-verification (checksum) step and secure communications (HTTPS) to ensure data integrity and confidentiality.

**What did you do well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?**  
I did especially well at quickly identifying the missing cryptographic support and insecure HTTP communication, then selecting the right modern solution (SHA-256) and clearly justifying it. Coding securely is critical because a single vulnerability can lead to data breaches, financial loss, legal penalties, and loss of customer trust. Strong software security adds real business value: it protects client data, meets regulatory requirements, reduces the risk of costly incidents, and builds long-term customer confidence — directly supporting Artemis Financial’s mission that “Security is everyone’s responsibility.”

**Which part of the vulnerability assessment was challenging or helpful to you?**  
The most helpful part was performing the secondary static analysis with the Maven dependency-check plugin after every change — it gave me immediate, objective feedback that no new vulnerabilities were introduced. The most challenging part was initially configuring the self-signed certificate and keystore correctly so the application would run on HTTPS port 8443 without errors, but once I got it working it became one of my favorite parts of the project.

**How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?**  
I added multiple layers of security in an iterative process:  
1. Implemented SHA-256 hashing for file integrity verification.  
2. Generated a self-signed RSA 2048-bit certificate and configured HTTPS.  
3. Added proper error handling with try-catch blocks.  
4. Performed static analysis and manual functional testing after each change.  

In the future I would continue using OWASP Dependency-Check and the NIST guidelines for vulnerability assessment, combined with tools such as SonarQube for code quality and manual threat modeling to decide the best mitigation techniques.

**How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?**  
I ensured functionality by manually testing the refactored application: the new checksum endpoint returned the expected secure hash containing my name, and the application started cleanly on HTTPS port 8443. I verified security by running a full Maven dependency-check scan after refactoring and confirmed zero new vulnerabilities. I also reviewed the code manually for syntax, logic, and security issues before final submission.

**What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?**  
- Java Keytool for certificate generation  
- Spring Boot security configuration (application.properties)  
- MessageDigest class for SHA-256 hashing  
- Maven dependency-check plugin (OWASP)  
- OWASP, NIST, and Spring Boot official documentation  
- Iterative testing after every code change  

These tools and the practice of “test after every change” will be part of every secure coding project I do going forward.

**Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?**  
I would proudly show this Practices for Secure Software Report. It demonstrates my ability to take real business requirements, choose and justify a strong cryptographic algorithm, implement secure communications (HTTPS), refactor production-style code, and verify security with industry tools — all while keeping the application fully functional. It shows I understand secure coding principles and can apply them end-to-end.

---

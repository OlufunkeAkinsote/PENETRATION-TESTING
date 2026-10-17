# PENETRATION-TESTING
Gained access medirozahospital.com and penetrate their office 

WEB APPLICATION PENETRATION TESTING REPORT

Prepared by: Olufunke Akinsote

Target Website: medirozahospital.com

Assessment Type: Black-Box Web Application Penetration Test

Project: NetworkWalks Cybersecurity Internship — Week 4 Final Project

Assessment Date: 15/10/2026

Report Status: Findings Based on Reported Test Results

Classification: Confidential — Sensitive Security Assessment

________________________________________
1. Executive Summary
This report documents the results of a web application penetration testing exercise targeting medirozahospital.com as part of the NetworkWalks Cybersecurity Internship Week 4 Final Project.

The assessment focused on identifying weaknesses that could allow unauthorized access to sensitive application data, protected files, and password-protected resources.

During the assessment, the reported test results indicated that patient information and staff salary information could be accessed. Encrypted files were also downloaded, and password-hash analysis was used to recover a password and obtain access to protected content.

These results indicate potentially significant weaknesses in data access controls, sensitive information protection, and password security. If the access occurred without appropriate authorization controls, the exposure could affect patient confidentiality, employee privacy, organizational security, and regulatory compliance.

The most significant concern is the reported access to patient and employee information. Healthcare organizations handle sensitive records that require strong access restrictions, secure storage, and appropriate monitoring. Exposure of such information could create privacy, legal, financial, and reputational consequences.

The assessment highlights the importance of enforcing server-side authorization, protecting confidential files, strengthening password security, and monitoring access to sensitive information.

Overall conclusion: The reported findings warrant urgent investigation and remediation. Final severity ratings should be confirmed against the exact resources accessed, the permissions of the test account, the evidence collected, and the extent of demonstrated access.

3. Scope and Methodology

2.1 Target and Scope
The target identified for this assessment was:
•	Website: medirozahospital.com
•	Assessment type: Black-box web application security testing
•	Primary focus: Access control, sensitive data exposure, file protection, and password security.
The reported assessment activities included:
1.	Examining the target application's accessible functionality.
2.	Identifying and accessing patient information.
3.	Accessing staff salary information.
4.	Downloading encrypted files.
5.	Performing password-hash analysis and using a recovered password to access protected content.
6.	Documenting observed security weaknesses and recommending remediation.
The assessment scope should be limited to the systems, accounts, files, and activities explicitly covered by written authorization.


2.2 Methodology
The assessment followed a structured security testing approach.
Phase 1 — Reconnaissance
The target application was examined to identify accessible resources, potential entry points, and relevant application functionality.
Phase 2 — Access Control Testing
Application resources were examined to determine whether access restrictions adequately protected sensitive patient and employee information.
Phase 3 — Sensitive File Assessment
Encrypted files were identified and downloaded during the reported testing. Their protection mechanisms and the implications of obtaining access were considered.
Phase 4 — Password and Hash Analysis
Password-hash analysis was performed, and a password was reportedly recovered and used to obtain access to protected content.
Phase 5 — Evidence Documentation
The reported results were organized into findings covering unauthorized information access, file protection, and password security. Supporting evidence should include sanitized screenshots, relevant request and response records, and tool output.
Phase 6 — Risk Assessment and Remediation
The potential impact of each finding was evaluated, and corrective measures were identified to reduce the risk of data exposure and unauthorized access.
2.3 Limitations
This report is based on the results described by the assessor. Exact endpoints, technical evidence, encryption methods, hash algorithms, and the specific content accessed have not yet been supplied.
Consequently, the findings below reflect reported observations. Technical root causes and final severity ratings should be confirmed during evidence review.
3. Findings and Proof of Exploitation
Finding 1: Access to Patient Information
Finding ID: WEB-01
Category: Sensitive Data Exposure / Broken Access Control
Provisional Severity: Critical or High, pending validation
Description
During the assessment, access to patient information was reportedly obtained through the target application.
Patient records can contain highly sensitive personal and medical information. If these records are accessible to users who do not have the required permissions, the application may have inadequate access-control enforcement or another weakness that exposes confidential information.
Potential Impact
•	Breach of patient confidentiality.
•	Exposure of sensitive personal or medical information.
•	Potential privacy and regulatory consequences.
•	Increased risk of identity misuse or other targeted attacks.
•	Reputational damage and loss of trust.
Proof of Exploitation
The reported test result was successful access to patient information.
The final evidence record should include:
•	The affected application endpoint or resource category.
•	The access conditions and account permissions used during testing.
•	A sanitized screenshot or HTTP response demonstrating the access.
•	Whether the information was accessible without authentication or through an account lacking the necessary permissions.
•	The validation date and final test result.
Patient names, medical record numbers, diagnoses, and other identifying details should not appear in the report.
Recommendation and Remediation
1.	Enforce server-side authorization checks for all patient-related resources.
2.	Apply role-based access control and least-privilege permissions.
3.	Verify that users can access only records they are explicitly authorized to view.
4.	Review API endpoints and direct resource references for authorization failures.
5.	Log and monitor access to sensitive patient records.
6.	Investigate the extent of exposure and follow the organization's incident response and privacy procedures.
Retest Criteria: Requests from unauthorized users must be denied, and authorized users must only be able to access records within their permitted scope.
________________________________________
Finding 2: Access to Staff Salary Information
Finding ID: WEB-02
Category: Sensitive Employee Data Exposure / Broken Access Control
Provisional Severity: High, pending validation
Description
The assessment reportedly allowed access to staff salary information.
Salary and compensation records are confidential employee information. If accessible to users without appropriate authorization, the exposure may indicate inadequate access restrictions around human resources records, payroll resources, or related application functionality.
Potential Impact
•	Breach of employee privacy.
•	Exposure of confidential compensation information.
•	Internal disputes or targeted social engineering.
•	Potential financial or reputational harm.
•	Unauthorized disclosure of other employee records if the same weakness affects additional resources.
Proof of Exploitation
The reported result was successful access to staff salary information.
Evidence should establish the resource accessed, the permissions of the testing account, the observed application response, and whether the information was outside the account's authorized access.
Any screenshots or exported records should be sanitized to remove employee identities, individual salaries, account details, and other confidential information.
Recommendation and Remediation
1.	Restrict salary and payroll resources to explicitly authorized HR, payroll, and management roles.
2.	Enforce server-side permission checks for every request.
3.	Separate payroll and employee administration functions from general user functionality.
4.	Audit existing permissions and remove excessive privileges.
5.	Review access logs for unexpected access to compensation records.
6.	Investigate whether other confidential employee information was exposed.
Retest Criteria: Users without the required role must be unable to retrieve staff salary information through the interface, direct URLs, or API requests.
________________________________________
Finding 3: Download of Encrypted Files
Finding ID: WEB-03
Category: Sensitive File Exposure / Security Misconfiguration
Provisional Severity: High, pending validation
Description
Encrypted files were reportedly downloaded during the assessment.
Encryption can protect information when files are stored or transmitted, but encryption alone does not prevent unauthorized file downloads. If sensitive files are accessible to unauthorized users, the application may have weaknesses in file access controls, storage configuration, or resource authorization.
The actual impact depends on the contents of the files, the encryption method, the security of the encryption keys, and whether the files could be decrypted.
Potential Impact
•	Unauthorized possession of confidential files.
•	Potential disclosure if the encryption protection is weak or the relevant password is recovered.
•	Exposure of additional sensitive information if files contain patient, employee, or system records.
•	Increased opportunities for further compromise.
Proof of Exploitation
The reported result was the successful download of encrypted files.
The evidence record should identify the file category, the access conditions, the server response, and whether the files could be opened or decrypted. File names and contents should be redacted if they reveal confidential information.
Recommendation and Remediation
1.	Store sensitive files outside publicly accessible directories where practical.
2.	Enforce server-side authorization before every file download.
3.	Use secure, non-guessable resource identifiers alongside proper authorization checks.
4.	Encrypt sensitive information using established cryptographic methods and secure key management.
5.	Protect encryption keys separately from the encrypted data.
6.	Review file access logs and restrict unnecessary file access.
7.	Investigate whether any downloaded files contained patient records, employee information, or credentials.
Retest Criteria: Unauthorized requests must be denied, and sensitive files must not be retrievable by users without the necessary permissions.
________________________________________
Finding 4: Password Recovery Through Hash Analysis
Finding ID: WEB-04
Category: Weak Password Security / Credential Exposure
Provisional Severity: High, pending validation
Description
During the reported assessment, password-hash analysis was used to recover a password. The recovered password was then used to gain access to protected content.
This result demonstrates that the tested password or password-protection mechanism was susceptible to the method used in the assessment. The precise root cause requires further evidence. Potential contributing factors include weak password selection, inadequate password-hashing configuration, or insufficient protection of password hashes.
Recovering a password for an encrypted file does not, by itself, establish that an application account was compromised. The affected resource and the scope of the recovered credential must be identified in the final report.
Potential Impact
•	Unauthorized access to password-protected files or resources.
•	Exposure of confidential information protected by the recovered password.
•	Increased risk if the password is reused for other accounts or services.
•	Potential expansion of access if the recovered credential provides additional privileges.
Proof of Exploitation
The reported result was successful password recovery through hash analysis, followed by access to protected content.
The final evidence should document:
•	The type of password hash or protection mechanism, if known.
•	The authorized test method and tool used.
•	The result showing that a password was recovered.
•	The type of protected resource subsequently accessed.
•	Whether the recovered password was specific to a document or associated with an application account.
Do not include the recovered password, a usable hash, or other authentication secrets in the report.
Recommendation and Remediation
1.	Replace weak passwords with strong, unique credentials.
2.	For application account passwords, use modern password-hashing algorithms such as Argon2id, scrypt, or appropriately configured bcrypt or PBKDF2, with unique salts.
3.	Use a suitable work factor for the selected password-hashing scheme.
4.	Restrict access to password hashes and other authentication material.
5.	Enable multifactor authentication for sensitive accounts.
6.	Rotate any credentials confirmed to be exposed and investigate potential password reuse.
7.	Review document encryption and key-management practices separately from application authentication.
Retest Criteria: Confirm that the relevant password-storage or protection mechanism has been strengthened and that the previously demonstrated recovery method no longer succeeds under the documented test conditions.
4. Risk Rating
4.1 Rating Approach
Severity should be assigned based on demonstrated impact, exploitability, data sensitivity, access required, and the extent of exposure.
Severity	Meaning
Critical	Demonstrated compromise with severe consequences, such as broad exposure of highly sensitive records or extensive control of critical systems
High	Significant unauthorized access or exposure of sensitive information
Medium	Limited impact or exploitation requiring additional conditions
Low	Limited security impact
Informational	Security improvement opportunity without a demonstrated direct vulnerability
4.2 Preliminary Risk Register
ID	Finding	Provisional Rating	Priority
WEB-01	Access to patient information	Critical / High	Urgent
WEB-02	Access to staff salary information	High	Urgent
WEB-03	Download of encrypted files	High, subject to contents and protection	High
WEB-04	Password recovery through hash analysis	High, subject to scope of access	High
These ratings are provisional. The patient information finding should be rated Critical only if the evidence supports the scale and consequences of the demonstrated exposure. The encrypted-file finding also depends on whether unauthorized access was confirmed and whether the encryption could be defeated.
The final report should distinguish confirmed exploitation from potential consequences and should not imply that all patient records, employee records, or application accounts were compromised unless the evidence establishes that scope.
5. Recommendations and Remediation Plan
5.1 Immediate Remediation
Priority 1 — Protect patient and employee information
•	Restrict access to patient and payroll records.
•	Correct any confirmed authorization failures.
•	Review access logs for unusual or unauthorized retrievals.
•	Investigate the scope of exposed information.
•	Follow applicable organizational incident response, privacy, and reporting procedures.
Priority 2 — Secure files and credentials
•	Restrict access to sensitive files and backups.
•	Review file encryption and key management.
•	Rotate confirmed exposed credentials.
•	Review password storage and password strength.
•	Revoke unnecessary access to sensitive resources.
5.2 Technical Remediation
Security Area	Required Action	Verification Method
Patient data	Enforce record-level authorization	Test access using accounts with different permissions
Salary information	Restrict payroll functions and resources	Confirm unauthorized roles cannot retrieve compensation data
Encrypted files	Enforce download authorization and secure storage	Confirm unauthorized file requests are denied
Password security	Strengthen password storage and credential controls	Review configuration and repeat authorized password-security tests
Monitoring	Log access to sensitive records and files	Confirm relevant events are recorded and alerts are generated as designed
5.3 Remediation Verification
Following remediation, conduct an authorized retest to confirm that:
1.	Patient information is accessible only to appropriately authorized users.
2.	Staff salary information is restricted to approved roles.
3.	Sensitive files cannot be downloaded without the necessary permissions.
4.	Password protection and credential storage meet the applicable security requirements.
5.	Relevant access attempts are logged and can be investigated.
Record each retest result as Pass, Fail, or Inconclusive, with supporting evidence.
6. Conclusion
The reported penetration testing results for medirozahospital.com indicate potentially serious security weaknesses involving access to patient information, employee salary information, encrypted files, and password-protected content.
The reported recovery of a password through hash analysis further demonstrates the importance of evaluating password strength and the security of stored password hashes or other protection mechanisms.
If these activities demonstrated access beyond the permissions granted to the assessor, the findings represent significant confidentiality risks and should be prioritized for investigation and remediation.
The assessment reinforced the importance of effective access control, secure file handling, strong password protection, and evidence-based vulnerability validation.
The recommended next steps are to confirm the technical root cause of each finding, establish the extent of any unauthorized exposure, implement the proposed corrective measures, and verify their effectiveness through a controlled retest.
This project provided practical experience in web application assessment, vulnerability analysis, evidence documentation, and risk-based remediation planning.
7. Evidence Register
Attach only sanitized evidence from the actual assessment.
Evidence ID	Finding	Required Supporting Evidence
E-01	WEB-01	Redacted response or screenshot demonstrating access to patient information
E-02	WEB-02	Redacted response or screenshot demonstrating access to staff salary information
E-03	WEB-03	Evidence of the file download and its access conditions
E-04	WEB-04	Sanitized password-hash analysis result and evidence of access to protected content
E-05	All findings	Retest evidence following remediation
Evidence Handling
•	Do not attach unredacted patient records or payroll information.
•	Do not include recovered passwords, reusable hashes, session tokens, or private encryption keys.
•	Preserve original evidence securely in accordance with the assessment authorization and applicable procedures.
•	Do not access additional records merely to increase the volume of evidence.
•	Record only the minimum information needed to establish each finding.
End of Report


 

 

 

 
 

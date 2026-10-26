Project Overview & Client Summary
Artemis Financial is a regional financial consulting firm that delivers personalized financial planning, investment management, and tax analysis services. To modernize operations, the company commissioned a custom RESTful web service to securely deliver financial data to authorized clients. Because Artemis deals with sensitive financial and personally identifiable information (PII), their primary mandate was to ensure data confidentiality, data integrity, and compliance with modern software security standards. The company requested a comprehensive security assessment of their software architecture, identification and mitigation of critical vulnerabilities, and the implementation of strong encryption and secure communication channels.

Secure Coding Practices & Business Value
During the vulnerability assessment, I effectively combined automated dependency scanning with manual code reviews to trace vulnerabilities from root cause to remediation. Writing secure code from the ground up is critical because retrofitting security into an existing architecture is significantly more expensive, error-prone, and disruptive than building defenses into the design phase. For any enterprise, and financial institutions in particular, proactive software security protects organizational integrity, safeguards client trust, prevents devastating data breaches, ensures regulatory compliance, and shields the business from substantial financial penalties and brand damage.

Vulnerability Assessment Insights
Helpful: Using the OWASP Dependency-Check Maven plugin proved invaluable. It automatically cross-referenced third-party libraries against the National Vulnerability Database (NVD) and Common Vulnerabilities and Exposures (CVE) registries, uncovering hidden transitive vulnerabilities in dependencies that manual line-by-line code review would likely have missed.

Challenging: The primary challenge was deciphering false positives from actual exploitable risks within the dependency tree, as well as resolving library version conflicts when updating outdated, vulnerable Maven dependencies without breaking existing functionality.

Defense in Depth & Mitigation Strategy
To establish defense in depth, I increased layers of security across the application stack:

Transport Layer Security: Enforced HTTPS with a modern TLS protocol configuration, generating and binding a secure self-signed digital certificate in Java KeyStore (JKS) format to encrypt all client-server communications in transit.

Data Integrity & Verification: Implemented SHA-256 cryptographic hashing algorithms within the service logic to generate verifiable checksums for sensitive data, ensuring payload integrity and non-repudiation.

Dependency Hardening: Remediated known Common Weakness Enumerations (CWEs) by updating vulnerable libraries in pom.xml.

In future software projects, I will continue leveraging the OWASP Top 10 framework, automated Static Application Security Testing (SAST), Software Composition Analysis (SCA) tools, and CVSS (Common Vulnerability Scoring System) severity matrices to prioritize and apply targeted mitigation techniques.

Verification & Vulnerability Management Post-Refactoring
To guarantee that the application remained fully functional while secure:

Functional Testing: I executed targeted API endpoint calls (GET/POST requests) across both HTTP and HTTPS to confirm that secure endpoints responded properly, data payloads were received intact, and unauthorized or plaintext traffic was rejected.

Regression & Vulnerability Checks: After refactoring the source code and configuration files, I re-ran mvn clean compile alongside the OWASP Dependency-Check plugin. This re-scan verified that no new vulnerabilities or compromised transitive dependencies were introduced during remediation.

Tools, Practices, and Future Takeaways
Tools & Frameworks: Java Spring Boot, Apache Maven, OWASP Dependency-Check plugin, Java Keytool, and cryptographic hashing utilities (MessageDigest).

Coding Practices: Adherence to the Principle of Least Privilege, robust input validation, secure default configurations, avoiding hardcoded secrets, and maintaining an up-to-date Software Bill of Materials (SBOM). These practices will serve as standard guidelines for future backend architectures and secure API designs.

Portfolio Showcase
This assignment demonstrates my ability to conduct comprehensive security audits, translate theoretical security frameworks (OWASP/NIST) into actionable engineering fixes, and implement cryptographic safeguards in a production-oriented Java Spring Boot application. To prospective employers, this project serves as concrete evidence of:

Software Composition Analysis (SCA) and vulnerability remediation reporting.

Secure REST API development using modern TLS/SSL configurations.

Cryptographic data integrity verification (SHA-256).

The ability to balance operational functionality with rigorous security standards.

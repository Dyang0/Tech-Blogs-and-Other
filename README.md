# Helpful-Resources

[So You Want To Be a Pentester?](https://jhalon.github.io/becoming-a-pentester/)

## Code Review

 Why Code Review?
 -  Tools can be used to perform this task but they always need human verifcation. They do not understand context, which is the keystone of security code review. Tools are good at assessing large amounts of code and pointing out possible issues, but a person needs to verify every result to determine if it is a real issue, if it is actually exploitable, and calculate the risk to the enterprise. Human reviewers are also necessary to fll in for the signifcant blind spots, which automated tools, simply cannot check
 -  There are also privacy, compliance and stability and availability concerns, which may not covered by penetration testing, but can be covered in code reviews
 -  . Data information leakage in a cloud environment for example may not be discovered, or allowed, via a penetration test. Therefore penetration testing should be seen as an important tool in the arsenal, but alone it will not ensure product software is secure.

[Code Injection](https://owasp.org/www-community/attacks/Code_Injection)
- Is limited to the language being used. Different than command injection where a shell can be used

[Buffer Overflow Attacks](https://owasp.org/www-community/attacks/Buffer_overflow_attack)
- what are the difference with safer counterparts? (gets() vs. fgets())
- Suspectible in lower level languages (C & C++)

[OWASP Top 10](https://owasp.org/www-project-top-ten/)

[OWASP Code Review Guide](https://owasp.org/www-project-code-review-guide/)

- [PDF](https://owasp.org/www-project-code-review-guide/assets/OWASP_Code_Review_Guide_v2.pdf)

## Notes
- software has metrics of performance, scalability, and maintainability. Secure code also measures the maturity of the software. This is just as important for larger companies.

The term “360 review” refers to an approach in which the results of a source code review are used to plan and execute a penetration test, and the results of the penetration test are, in turn, used to inform additional source code review

<img width="378" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/4ea91b17-e7dd-4363-82c0-e661def8f9c6">

- knowing the internal code through a code review and using that knowledge to form test and abuse cases is known as white boxing (also clear or glass box testing). With the prior knowledge, penetration testing can be easier

Potential Pros and Cons of White Boxing

Pros
- Can lead to a more productive penetration test, since testing can be focused on suspected or even known vulnerabilities. Using knowledge of the specifc frameworks, libraries and languages used in the web application, the penetration test can concentrate on weaknesses known to exist in those frameworks, libraries and languages
- Even though a vulnerability found during the code review is not exploitable, it can later be if a protective measure is changed in the future
- A code review may be effective when there's a risk of insiders attacking
- The results of the penetration test can then be used to target additional areas for code review
*Besides addressing the par-ticular vulnerability exploited in the test, it is a good practice to look for additional places where that same class of vulnerability is present, even if not explicitly exploited in test. For instance, if output encoding is not used in one area of the application and the penetration test exploited that, it is quite possible that output encoding is also not used elsewhere in the application

Cons
- A vulnerability found during code review may turn out not to be exploitable during penetration test due to the code reviewer(s) not considering a protective measure (input validation, for instance). May be a lower risk due to lower exposure
- It is unrealistic that an attacker would be given access to the target web application’s source code and advice from its developers. Thus, the risk that an outside attacker could exploit the vulnerabilities found by the white box penetration tester is probably lower.


 Implicit Advantages of Code Review to Development Practices
 1. Provides an historical record
 2. Verifcation that the change has been tested
 3. Coding education for junior developers
 4. Familiarization with code base
- When a new feature is developed, it is often integrated with the main code base, and here code review can be a
conduit for the wider team to learn about the new feature and how its code will impact the product. This helps
prevent functional duplication where separate teams end up coding the same small piece of functionality
5. Pre-warning of integration clashes

- With coding guidelines there might be someone from the security team reviewing code to ensure code reviews keep security in mind

- security code review is not just about scanning the code for set of unknown insecure code patterns but it also involves understanding the code implementation of the application and enumerating the flaws specifc to it

- The term ‘source to sink analysis’ means to determine all possible inputs to the application (source) and how they are being processed by it (sink). A sink could be an insecure code pattern like a dynamic SQL query, a log writer, or a response to a client device

- Once a faw is identifed, the reviewer must enumerate all the possible instances present in the application. This would not be a code review initiated by a code change, this would be a code scan initiated by management based on a faw being discovered and resources being committed to fnd if that faw exists in other parts of the product. For example, an application can be vulnerable to XSS vulnerability because of use of un-validated inputs in insecure display methods like scriptlets ‘response.write’ method, etc. in several places

Many organizations with responsibility for safeguarding the integrity, confdentiality and availability of their software and data need to meet regulatory compliance. This compliance is usually mandatory rather than a voluntary step taken by the organization. Compliance regulations include:
• PCI (Payment Card Industry) standards
• Central bank regulations
• Auditing objectives
• HIPPA

Factors to Consider when Developing a Code Review Process
1. Risks
2. Purpose & Context
3. Lines of Code
4. Programming language
5. Resources, Time & Deadlines

Reasons for Secure Code Reviews
1. it is proven to be cost efective and provides an additional level of security that static analyzers cannot provide. This justifies the potential complexity and cost of security
2. companies are driven by regulations and must have secure code to avoid fines

What Should a Code Review Report Include?
Date of review.
• Application name, code modules reviewed
• Developers and code reviewer names
• Task or feature name, (TFS, GIT, Subversion, trouble ticket, etc.)
• A brief sentence(s) to classify and prioritize software vulnerability if any and what if any remedial
tasks need to be accomplished or follow up is needed.
• Link to documents related to task/feature, including requirements, design, testing and threat
modeling documents.
• Code Review checklist if used, or link to organization Code Review Checklist. (see Appendix A)
• Testing the developer has carried out on the code. Preferably the unit or automated tests themselves can be part of the review submission.
• If any tools such as FxCop, BinScope Binary Analyzer, etc. were used prior to code review.


# Posting on Medium Until I Get A Job

- [Posting on Medium Until I Get A Job (Update 1: Beginning)](https://medium.com/@dyang./posting-on-medium-until-i-get-a-security-job-update-1-beginning-294ba5411370)
- [Posting on Medium Until I Get A Job (Update 2: Networking & TCP/IP)](https://medium.com/@dyang./posting-on-medium-until-i-get-a-job-update-2-networking-tcp-ip-63aed0aef48b)
- [Posting on Medium Until I Get A Job (Update 3: The Realization)](https://medium.com/@dyang./posting-on-medium-until-i-get-a-job-update-3-the-realization-b1e3884a8821)
- Update 4 [IN PROGRESS]

*The "General Notes" below are used to help me organize my thoughts for this Medium series. Disregard them







-
### General Notes

[So You Want To Be a Pentester?](https://jhalon.github.io/becoming-a-pentester/)

### Code Review

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
- Application name, code modules reviewed
- Developers and code reviewer names
- Task or feature name, (TFS, GIT, Subversion, trouble ticket, etc.)
- A brief sentence(s) to classify and prioritize software vulnerability if any and what if any remedial tasks need to be accomplished or follow up is needed
- Link to documents related to task/feature, including requirements, design, testing and threat modeling documents
- Code Review checklist if used, or link to organization Code Review Checklist. (see Appendix A)
- Testing the developer has carried out on the code. Preferably the unit or automated tests themselves can be part of the review submission
- If any tools such as FxCop, BinScope Binary Analyzer, etc. were used prior to code review

When to Code Review
1. When code is about to be checked in (pre-commit)
2. When code has just been checked into a code base (post-commit)
3. When code audits are done

Dichotomy of Secure Code Review

- Many companies have security teams that do not have members with coding backgrounds, which can make interactions with development teams challenging. Because of this development teams are usually skeptical of security input and guidance. Security teams are usually willing to slow things down to ensure confdentiality and integrity controls are in place while developers are face with pressure from business units they support to create and update code as quickly as possible. Unfortunately the more critical the application to operational or business needs, the more pressure to deploy the code to production.
- It is best to weave secure code reviews into the SDLC processes so that development organizations do not see security as a hindrance, but as an assistance. As mentioned previously, spreading secure coding SMEs throughout an organization (satellites in BSIMM terminology) allows the secure code review tasks to scale and reach more development teams. As the process grows, more of the developers gain awareness of secure coding issues (as they have reviews rejected on secure coding grounds) and the frequency of secure coding issues in code reviews should drop.
  
A Risk Based Approach to Code Review
- Typically the intensity of the code review varies based on the perceived risk that the change presents
- Ultimately management is responsible for the output of a company, and thus they are responsible for the risk associated with products sold by the company

<img width="913" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/fbda3a0b-8a50-402f-97d3-72491ced73a2">

<img width="912" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/faffb019-9587-43f3-8ed5-4723c8232a2d">

<img width="925" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/e291371b-ed4b-4326-8010-870e5633caf6">

Code Review Preparation
- A security review of the application should uncover common security bugs as well as the issues specifc to business logic of the application. In order to efectively review a body of code it is important that the reviewers understand the business purpose of the application and the critical business impacts. The reviewers should understand the attack surface, identify the diferent threat agents and their motivations, and how they could potentially attack the application

How a Reviewer Can Effectively Review Code
1. Application features and Business Rules
2. Context
3. Sensitive Data
4. User roles and access rights
5. Application type
6. Code
7. Design
8. Company Standards and Guidelines

It is also about the data

- Security code review is not simply about the code structure. It is important to remember the data; the reason that we review code is to ensure that it adequately protects the information and assets it has been entrusted with, such
as money, intellectual property, trade secrets, or lives. The context of the data with which the application is intended to process is very important in establishing potential risk. If the application is developed using an inbuilt/well-known
design framework the answers to the most of these questions would be pre-defned. But, in case it is custom then this information will surely aid the review process, mainly in capturing the data fow and internal validations. Knowing the architecture of the application goes a long way in understanding the security threats that can be applicable to the application

- Most of the application designs are based on a concept of MVC. In such designs diferent components interact with each other in an ordered sequence to serve any user request. Design review should be an integral part of secure software development process. Design reviews also help to implementing the security requirements in a better way

- After understanding the design, the next phase is to analyze the threats to the design. This involves observing the design from an attacker’s perspective and uncovering the backdoors and insecure areas present in it

<img width="917" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/375401d7-93a3-477f-8736-90584759f7c9">

Code Review Checklist
- Data Validation
- Authentication
- Session Management
- Authorization
- Cryptography
- Error Handling
- Logging
- Security Confguration
- Network Architecture

Static Code Analysis
- such tools frequently serve as aids for an analyst to help them zero in on security relevant portions of code so they can fnd faws more efciently, rather than a tool that fnds all faws automatically
- bugs may exist due to insecure code, design, or configuration. Can be identified through two options
1. Static code scanner scripts based on a pattern search (in-house and open source)
2. Static code analyzers (commercial and open source)

- *Though code scanning scripts and open source tools can be efcient at fnding insecure code patterns, they often lack the capability of tracing the data fow. This gap is flled by static code analyzers, which identify the insecure code patterns by partially (or fully) compiling the code and investigating the execution branches, allowing for source to sink analysis. Static code analyzers and scanners are comprehensive options to complement the process of code review

<img width="917" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/f0659d9f-3aa2-4384-95d6-6d4e55555c16">

<img width="916" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/c8f2fd9c-944c-4f55-8909-d83bcc331d29">

<img width="916" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/1f766514-ce88-405d-b85e-fc05a0862230">

Application Threat Modeling

- Threat modeling is an in-depth approach for analyzing the security of an application. It is a structured approach that enables employees to identify, quantify, and address the security risks associated with an application. Threat modeling is not an approach to reviewing code, but it complements the secure code review process by providing context and risk analysis of the application

The threat modeling process can be decomposed into 3 high level steps:

1. Decompose the Application

Items to consider when decomposing the application include:
- External Dependencies

are items external to the code of the application that may pose a threat to the application

- Entry Points

defne the interfaces through which potential attackers can interact with the application or supply it with data.

- Assets

something that the attacker is interested in; these items/areas of interest are defned as assets

- Determining the Attack Surface

<img width="916" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/645d91fd-8e68-42cc-977a-2eece4334a05">

<img width="647" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/ce0020e0-f3fa-4035-9f45-d5e9ed8cd177">

- Trust Levels

represent the access rights that the application will grant to external entities

- Data fow analysis

Exploring the attack surface includes dynamic and static data fow analysis. Where and when variables are set and how the variables are used throughout the workfow, how attributes of objects and parameters might afect other data within the program. It determines if the parameters, method calls, and data exchange mechanisms implement the required security

- Transaction analysis

<img width="918" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/9d679c41-6175-420d-bc61-f83a49506ce3">

- Data Flow Diagrams

DFDs show how data moves logically through the system and allows the identifcation data entering or leaving the system along with the storage of data and the fow of control through these components

2.  Determine and rank threats

Critical to the identifcation of threats is using a threat categorization methodology. A threat categorization such as STRIDE can be used, or the Application Security Frame (ASF) that defnes threat categories such as Auditing & Logging, Authentication, Authorization, Confguration Management, Data Protection in Storage and Transit, Data Validation and Exception Management

The goal of the threat categorization is to help identify threats both from the attacker (STRIDE) and the defensive perspective (ASF). DFDs produced in step 1 help to identify the potential threat targets from the attacker’s perspective, such as data sources, processes, data fows, and interactions with users. These threats can be identifed further as the roots for threat trees; there is one tree for each threat goal

From the defensive perspective, ASF categorization helps to identify the threats as weaknesses of security controls for such threats. Common threat-lists with examples can help in the identifcation of such threats. Use and abuse cases can illustrate how existing protective measures could be bypassed, or where a lack of such protection exists

The determination of the security risk for each threat can be determined using a value-based risk model such as DREAD or a less subjective qualitative risk model based upon general risk factors (e.g. likelihood and impact)

The frst step in the determination of threats is adopting a threat categorization. A threat categorization provides a set of threat categories with corresponding examples so that threats can be systematically identifed in the application in a structured and repeatable manner

- Stride
Threat lists based on the STRIDE model are useful in the identifcation of threats with regards to the attacker goals. For example, if the threat scenario is attacking the login, would the attacker brute force the password to break the authentication? If the threat scenario is to try to elevate privileges to gain another user’s privileges, would the attacker try to perform forceful browsing? A threat categorization such as STRIDE is useful in the identifcation of threats by classifying attacker goals such as shown in table 8

<img width="913" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/e0fdf1fb-1462-46bd-9a69-d4ebe0bd5bb1">

It is vital that all possible attack vectors should be evaluated from the attacker’s point of view. For example, the login page allows sending authentication credentials, and the input data accepted by an entry point has to validate for potential malicious input to exploit vulnerabilities such as SQL injection, cross site scripting, and bufer overfows. Additionally, the data fow passing through that point has to be used to determine the threats to the entry points to the next components along the fow. If the following components can be regarded critical (e.g. the hold sensitive data), that entry point can be regarded more critical as well. In an end to end data fow the input data (i.e. username and password) from a login page, passed on without validation, could be exploited for a SQL injection attack to manipulate a query for breaking the authentication or to modify a table in the database

<img width="931" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/9d880171-3d2d-4253-927d-c565dda9e30a">

Microsoft DREAD threat-risk ranking model

- In the Microsoft DREAD threat-risk ranking model, the technical risk factors for impact are Damage and Afected Users, while the ease of exploitation factors are Reproducibility, Exploitability and Discoverability. This risk factorization
allows the assignment of values to the diferent infuencing factors of a threat. 

<img width="785" alt="image" src="https://github.com/Dyang0/Helpful-Resources/assets/70818105/b18a9a83-90ad-426a-9fe4-f4051829ee3c">

3. Determine countermeasures and mitigation

SQL Injection

The most common injection vulnerability is SQL injection. Injection vulnerability is also easy to remediate and protect against. This vulnerability covers SQL, LDAP, Xpath, OS commands, XML parsers

- Using string concatenation to generate a SQL statement is very common in legacy applications where developers were not considering security. The issue is this coding technique does not tell the parser which part of the statement is code and which part is data. In situations where user input is concatenated into the SQL statement, an attacker can modify the SQL statement by adding SQL code to the input data.

1. Blind SQL Injection
2. Parameterized SQL Queries

Parameterized SQL queries (sometimes called prepared statements) allow the SQL query string to be defned in such a way that the client input can’t be treated as part of the SQL syntax

Safe String Concatenation?

- So does this mean you can’t use string concatenation at all in your DB handling code? It is possible to use string concatenation safely, but it does increase the risk of an error, even without an attacker attempting to inject SQL syntax into your application.

- You should never use string concatenation in combination with the client input value. Take an example where the existence (not the value) of a client input variable “surname” is used to construct the SQL query of the prepared statement;


### Key Terms
- Secure Software Development Cycle (S-SDLC)
- Agile vs. Waterfall
- White box testing
- Capability Maturity Model (CMM)
- MVC (Model-View-Controller)
- use vs abuse cases



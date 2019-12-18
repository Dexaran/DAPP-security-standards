# DAPP Security Standards

The purpose of this repo is to highlight the security issues as well as provide DApp developers with the necessary information to launch their project securely or mitigate any issues that may occur.

Feel free to contact me if you have any questions or feedback dexaran@callisto.network / dexaran@ethereumclassic.org 

# General notes

[Nothing can be absolutely secure](https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=922194) (general paradigm of system security engineering). 

In this particular case the paradigm translates into:

>There is no single method of proving safety of a system. The system must rely on multiple methods of security enhancements. The more security enhancement practices are applied - the better.


There is no single universal method that is sufficient to ensure software security. None of formal verification, security audits, development of better programming languages, upgradeability of smart-contracts or any other measures can guarantee absolute safety of your software implementation. **Statement that a particular party is offering services that can guarantee complete safety of DApp is either a myth, a lie or a marketing move.**

A combination of security improvement methods and measures can significantly reduce the risk of DApp being hacked. Each security improvement strategy introduces a new layer of safety and it is strongly advised to rely on multiple "security layers". It may be even better to focus on system [fault-tolerance](https://en.wikipedia.org/wiki/Software_fault_tolerance) instead of trying to make it unhackable.

In the case of DApp, **fault tolerance** is the ability of DApp being fixed/debugged in case of detection of malicious activity.

When it comes to evaluating security enhancement methods it proves that [security audit](https://en.wikipedia.org/wiki/Information_technology_security_audit) is one of the most efficient methods albeit the most expensive one.

# Security improvement practices

Here I'd like to highlight the most common measures that a DApp developer must consider to improve the security aspect of the DApp:

- **Develop open-source applications.** Making your application open-source increases the level of security and ensures the ability to perform such security enhancement methods as "bug bounty" which further increases the overall level of system safety. There is a misconception that hiding the source codes of the system from public can prevent flaws and vulnerabilities from being exploited. This misconception is known as [security through obscurity](https://en.wikipedia.org/wiki/Security_through_obscurity).

- **Security audit.** Security audit is a peer review of the smart-contract code performed by a third party expert or a team of security experts. This proves to be one of the most efficient methods as it can cover any type of logical and application-specific mistakes. There are specialized companies offering security auditing services for smart-contract developers.

- **Bug bounty.** Bug bounty is a practice of publishing the source codes for community review and offering rewards for reporting the found vulnerabilities or flaws. Bug bounty is also a very efficient method of ensuring the system security if handled properly. The reward for finding a vulnerability must match the amount of work performed by the reviewer as well as match the level of harm that could be inflicted in case of reviewer deciding to exploit the vulnerability instead of reporting it.

- **Manual testing and testnet deployment.** Test your software. Test it more. Let smart-contract developers and all team members try the system with their own hands. Publish a version of the system at testnet and let community use it for a couple of months before the final release. This will definitely reduce the risk of vulnerabilities arising in the final version of the software. This is not a self-sufficient method of security improvement but it is cheap and efficient enough.

- **Automated testing.** Automated testing or [unit testing](https://en.wikipedia.org/wiki/Unit_testing) involves the development of a special software that will interact with the DApp for the sake of detection of any flaws and ensuring the correctness of DApps responses on any type of input. The effectiveness of this approach obviously depends on the correctness of the implementation of the testing software. In general automated tests are an auxiliary tool that can  reduce the overhead of security auditors/community reviewers/software testers. Automated testing can cover the routinuous cases of general software utility but it proves to be bad when it comes to identifying logical mistakes/ business model flaws or any other application-specific kind of potential threats. Automated tests are not a reliable measure of ensuring the overall system safety. These must be combined and used alongside other security enhancement procedures.


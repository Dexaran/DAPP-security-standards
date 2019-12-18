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

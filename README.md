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

- **Automated anomaly detection.** In case of DAPP the [anomaly detection](http://ids.cs.columbia.edu/sites/default/files/34880014.pdf) is a special feature of the smart-contract that automatically triggers countermeasures/alarms when unwanted behavior occurs in the smart-contract. In some cases it is possible to predict what kind of behavior is malicious and implement a "detection feature" and "contract disabling trigger". For example if you have developed a  casino and one player is winning 30 times in a row then it is obvious that he may be cheating and further investigation is necessary. It may be worth to disable the smart-contract thus disallowing the malicious player to drain it in case he is exploiting a vulnerability of the contract. The anomaly detection may be implemented as a kind of [watchdog service](https://www.webopedia.com/TERM/W/watchdog.html) and operated by third party offchain service without a need to implement it in smart-contract logic. The effectiveness of this method depends on the ability of smart-contract developer to determine which kind of activity should be considered "anomaly". This method is very good for preventing application-specific faults but it is not sufficient on its own. This practice should be used in combination with other security improvement measures.

- **Manual testing and testnet deployment.** Test your software. Test it more. Let smart-contract developers and all team members try the system with their own hands. Publish a version of the system at testnet and let community use it for a couple of months before the final release. This will definitely reduce the risk of vulnerabilities arising in the final version of the software. This is not a self-sufficient method of security improvement but it is cheap and efficient enough.

- **Automated testing.** Automated testing or [unit testing](https://en.wikipedia.org/wiki/Unit_testing) involves the development of a special software that will interact with the DApp for the sake of detection of any flaws and ensuring the correctness of DApps responses on any type of input. The effectiveness of this approach obviously depends on the correctness of the implementation of the testing software. In general automated tests are an auxiliary tool that can  reduce the overhead of security auditors/community reviewers/software testers. Automated testing can cover the routinuous cases of general software utility but it proves to be bad when it comes to identifying logical mistakes/ business model flaws or any other application-specific kind of potential threats. Automated tests are not a reliable measure of ensuring the overall system safety. These must be combined and used alongside other security enhancement procedures.

- **Formal verification.** [Formal verification](https://en.wikipedia.org/wiki/Formal_verification) much like the automated testing is an additional method of reducing the overhead for software testers/auditors/developers. This can be helpful in some cases but formal verification is not a self-sufficient method of ensuring system safety and must not be relied on.

- **Follow well-known programming practices.** Security is not a new area of programming and there are plenty of well-known mass-adopted methods and practices that are time proven already. **Adhere to coding standards. Comment your code.** It is strongly recommended for any contract developer to read the description of coding standards of the platform they intend to use. It is also recommended to read the respectable coding standards adopted by large-scale programming communities such as [GNU Coding Standard](https://www.gnu.org/prep/standards/standards.html). This is very important and it is not a matter of preferences! The coding standards are intended to make the logic represented by code pieces as straightforward as possible which greatly improves the ability of an auditor/software tester/code reviewer to identify and report a system flaw. The more readability of your code the better.

- **Make your application modular if possible.** Following this method of software development will improve the auditability of the code. This increases the effectiveness of auditing and testing as well. This may be hard with procedural programming languages as contrary to object-oriented practices. However dividing the program into independant modules allows for better testing/debugging and independant audits of each module. This also improves the upgradeability of the system which is important for fault-tolerance.

# Launching a DAPP following the best security practices

To ensure an adequate level of security, the DAPP developer must take the following steps in the sequence described.

0. Think about the coding standard and decide on it before you start so that all smart contracts are written in the same coding standard.

1. Develop your smart-contracts and comment the code if possible. It is way better to make it open-source and publish the results to the community for review. Consider adding an open-source license. Github is the right place to store your codes.

2. Once any functional part or application module is ready for use, you should begin public testing. Consider deploying a "work in progress" version to the public testnet. Test the operability of your DAPP there. Write unit tests if necessary.

3. As soon as your application development is finalized you should proceed with a security audit request and final testing. Find a security auditor and request the audit. Do not start the security audit when the application is still in development stage. Make sure that the DAPP development is finished and there will be no updates after the code is audited.

4. Announce the final testing and establish a feedback line. You should deploy the final stable version of the DAPP at testnet so that everyone could use it. The final testing stage may be handled at the same time the contract is undergoing the security audit. **It is very important to make community feedback collection as user-friendly as possible.** Take it seriously. It is better to set up multiple ways of collecting feedbacks including github, email, reddit thread and other public media. This is a very bad idea to require a user to register somewhere in order to provide his feedback regarding the usability of the DAPP or report any issues. You must respect your users time.Example: I'm competent enough to identify some bugs in DAPPs and I'm willing to report them but if I face a requirement to sign up on some forum that I'm not going to use (and I'm not going to use forums of every single project because I review hundreds of them each year) then I will give up and let developers resolve their problem on their own if they are not even capable of giving me a convenient way to submit the feedback so that I will not waste my time. I assume that most competent and well-paid developers will behave in the same way. Again, it is really important to introduce multiple feedback lines so that every user can find a convenient way to submit a bug report. This may save DAPP from a million dollar hack.

5. After the security audit is completed apply the necessary fixes/improvements if necessary. If there were major vulnerabilities reported and the applied fix has modified a significant part of the code then you should repeat steps 3 and 4. Keep in mind that modifying the code after the security audit will leave DAPP in unaudited stage and require a repeated auditing. If your software is modular, you can send only the modified module for re-audit, which will save you from the unnecessary time and resources spent on re-auditing already verified parts of the code.

6. After the software has passed the security audit you should announce the bug bounty (if your application is open source). This is better to proceed with the bug bounty after the security audit since most mistakes will be reported by auditors already.  Bugbounty is a precautionary measure, at this stage your program is already considered safe after testing and audit so the rewards for reporting bugs must be high. Bugbounty will help in case auditors have missed some kind of mistake. Normally the reward for reporting a bug/vulnerability depends on its severity. In most cases vulnerabilities are classified as [critical, high, medium and low severity](https://www.atlassian.com/trust/security/security-severity-levels). The reward for finding a vulnerability must mostly depend on the risk that the vulnerability poses to for the DAPP but not on the amount of work being done to report it. Assuming that you can lessen the reward for reporting vulnerabilities that were easy to find will result in more incentives to exploit the vulnerability than to report it. If you think that your DAPP is perfectly secure and the bugbounty is an unnecessary rigorous process then it is advised that you put a million dollar reward for finding a high severity vulnerability and let it run for a week.

7. Schedule a timeframe for the pre-release bug bounty depending on the scale of your DAPP. Small DAPPs require less time to be reviewed thus the timeframes could be lessened. 10 day long bugbounty should be enough for most small/medium scale DAPPs.

8. When the time for passing the bugbount comes to an end, announce the results. If there were no major flaws/vulnerabilities reported then you should launch your DAPP and deploy the contract on the mainnet of the platform you are going to use. If some major security vulnerabilities were reported and the applied fix affected significant part of the code or DAPP logic then you should repeat from step 3.

9. Leave the public bug bounty open for participation forever. It is possible that someone will identify a flaw in your DAPP after months or even years of its operation on mainnet. In this case  a person will likely look for the ability to get reward in exchange for the flaw report. You should make your constant bug bounty transparently available for everyone so that your users know where to look.

10. Do not hesitate to publicly thank and mention the auditors, bug hunters and bug bounty participants. Reputation is valuable in security auditing area because auditors salary depend on reputation and this public mentions of auditor/bug finder will increase his/her reputation. Public announcements of paid rewards will also draw attention to your bug bounty programs which also increases the level of your safety.

#### It is much better to pay $20,000 of rewards for bug bounties than have $20,000,000 stolen by hackers. Stay safe and keep your customers safe.

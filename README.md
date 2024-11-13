1. Problem Statement
1.1 Problem Description
In recent decades, financial and technological innovations have flourished, bringing new opportunities but also unresolved challenges. Chief among these challenges is the concentration of market power in a few of the largest suppliers; intermediary fees charged by stockbrokers, exchanges, trading platforms, fund managers, financial advisors, and other intermediaries, etc. Among them, underbanked services have attracted much attention [10]. In the current financial landscape, users have certain requirements for real-time profits and deposit and withdrawal delays of deposits, demand transparency in interest calculations, the security of their deposits.  Traditional banking systems often lack transparency and trust mechanisms, leading to opaque interest calculations, inefficient fund management, and potential security risks. On the other hand, the banking industry has entered a period of vigorous development. As mentioned by RADOMIR [11], this has also relatively increased the competition among banks and the standards for gaining competitive advantages. As shown in the figure below, the asset size changes of various types of banks in China from 2019 to 2022. The year-on-year growth rate of large commercial banks did not exceed 10% between 2019 and 2021, which was lower than that of urban and rural commercial banks and joint-stock banks. As of December 2022, the total asset market share of the six state-owned commercial banks exceeded 164.11 trillion RMB, accounting for 65.12%, while the combined asset market share of joint-stock commercial banks and rural commercial banks reached 34.88%. The long-standing monopoly market position of large state-owned commercial banks no longer exists. That is why competition among banks is also a prerequisite for the continuous growth of the number of customers. 
 
Therefore, it is particularly important for banks to improve business quality and effectiveness. There is an urgent need to apply new blockchain technology to the business level, otherwise banks will face the risk of losing market share of competitors. This project aims to address these issues by developing a SimpleSavingsAccount based on smart contract technology to provide a decentralized, transparent, and secure financial solution.

1.2 Understanding the Problem
The complexity of traditional banking systems and the role of intermediaries can lead to various issues such as human errors, fraudulent activities, and inefficiency. Add to this the high fees, service charges and regulatory compliance costs of financial intermediaries, as well as delays, burdensome paperwork and opportunities for fraud and crime [4]. This problem is exacerbated by the large number of financial intermediaries [5], especially during periods of financial distress and high volatility [6]. Therefore, the banking industry is in urgent need of transformation and is seeking new growth paths. Blockchain applications also promote the formation of a "multi-center, weak intermediary" scenario, which will improve the efficiency of the banking industry [1]. Since blockchain is a breakthrough in data storage and information transmission, it may fundamentally change the existing financial and economic operation mode, which may lead to a new round of technological innovation and industrial transformation within the FinTech industry [2]. Blockchain technology can optimize the global financial infrastructure and achieve sustainable development, using more efficient systems than currently available to meet various financial needs. In fact, many banks are currently looking at blockchain technology to promote economic growth and accelerate the development of green technology [3].
At the same time, smart contract technology is reshaping traditional banking and business processes. Smart contracts are embedded in the blockchain, enabling the contractual terms of the agreement to be automatically executed without the intervention of a trusted third party. As a result, smart contracts can reduce management work and save service costs, improve the efficiency of business processes and reduce risks [8]. A smart contract is a computer program that is self-verifying, self-executing, and tamper-proof. That was proposed by Nick Szabo in 1994[7]. We hope that by leveraging smart contract technology, we can significantly reduce the problems in the banking industry.
Our group assignment is to create an automated interest calculation and fund management system using blockchain and smart contracts 	technology to enhance user trust and satisfaction.
1.3 Evaluation
The problem statement clearly identifies the shortcomings of the current financial system and highlights the potential and advantages of smart contracts in addressing these issues. For example, smart contracts bring transparency to banking: transaction records are encrypted and shared among users without the involvement of any third party, so the integrity of the data is beyond doubt [9]. This problem is highly relevant and significant, presenting both practical importance and technical challenges. Solving this problem can have a substantial impact on various aspects of society, improving the overall well-being of communities.
At the same time, optimizing the bank’s business also indirectly increases its competitiveness. According to Patti’s research, the increase in bank competitiveness helps the creation of new businesses [12], which can further promote social development, technological progress and economic development.
2. Creative Solution Design
2.1 Solution Design
To address the identified challenges, we have designed a SimpleSavingsAccount using Solidity smart contracts. This contract utilizes Ethereum blockchain technology to manage user deposits and interest calculations, featuring:
Users can deposit Ether by calling the deposit function, receiving a reward based on the deposit amount.
An interest rate of 0.0001% per second is automatically calculated on user deposits.
Users can withdraw deposits and accumulated interest by calling the withdraw function, ensuring transparency and security of funds.
Event mechanisms are used to record each deposit and withdrawal transaction for audit and tracking purposes.
The contract includes mechanisms for deposit rewards and early withdrawal penalties to encourage longer deposit durations.
2.2 Innovation and Feasibility
This solution innovatively combines blockchain's decentralized features with the automation capabilities of smart contracts, achieving transparent interest calculation and secure fund management. The smart contract code is concise and clear, facilitating audit and verification, thereby enhancing system credibility and user trust. The use of Python scripts and Slither tools for vulnerability detection ensures the security and stability of the code.
2.3 Consistency
The solution is closely aligned with the problem statement, directly addressing the deficiencies of traditional financial systems. By employing smart contract technology, we achieve transparent and automated fund management, showcasing the principles of blockchain and DeFi. This reflects the concepts of decentralization, minimized trust, and transparency, providing a more secure, transparent, and efficient financial service.
This response covers all aspects of the problem statement and creative solution design, demonstrating the potential and advantages of smart contracts in addressing real-world issues. 
3.	Implementation of a Blockchain Application
3.1 Basic Deposit Application
3.1.1Deposit and withdrawal functions
   SimpleSavingsAccount is a simple smart contract designed to provide a decentralized savings account service. Users can deposit ETH by calling a function in the contract and withdraw the principal plus the interest due when needed. Key features of the contract include: Decentralization: Based on the Ethereum blockchain, there is no need for a central authority to manage it. Transparency: All transaction records are publicly available, increasing the transparency of the system. Security: Utilize the technical features of smart contracts to ensure the safety of user funds
Users call this function to deposit ETH into their account. Check whether the deposit amount is greater than 0 to ensure that the user deposits a valid amount. Update the user's balance. The current time is recorded as the user's deposit time. Trigger the Deposit event to record the deposit activity
 
The user calls this function to withdraw the balance in their account plus the interest due. Calculate the user's current balance plus the interest due. Check if the amount requested by the user does not exceed the current balance plus interest. Update the user's balance. Transfer the corresponding ETH back to the user's address. Trigger the Withdrawal event to record the withdrawal activity.
3.1.2Calculate interest
  Calculate the specified user's current balance plus the interest due. Calculate the time difference (seconds) from the deposit to the present. The interest due is calculated based on the time difference and interest rate. Returns the user's current balance plus interest
Dynamic Calculation: Dynamically calculates the interest due based on the user's deposit time and balance, ensuring that it is fair and reasonable. Transparent inquiry: Users can check their balance and interest due at any time, improving the transparency of the system. Logic: Calculate the time difference (seconds) from the deposit to the present. The interest due is calculated based on the time difference and interest rate. Returns the user's current balance plus interest.
 
3.1.3Technical details
Two mapping tables, balances and depositTimes, are used to store the user's balance and deposit time, respectively. Set the interest rate at 0.0001% per second, which is 0.0001% per second. Two events, Deposit and Withdrawal, are defined to record the user's deposit and withdrawal activity
 
Detailed security review and optimization are required before actual deployment to ensure the robustness and security of the contract. Security review: Re-entrancy attack: Check the contract for the risk of re-entrancy attack to ensure that the user's balance is correctly updated before and after the transfer. Overflow/Underoverflow: Use the SafeMath library or other methods to prevent integer overflow or underoverflow. Permission control: Ensure that only the contract owner can modify key parameters, such as interest rates. Performance optimization: Event logging: Use event logging wisely to reduce unnecessary data storage. Computational optimization: For complex calculations, consider using external contracts or off-chain computations to improve efficiency.
SimpleSavingsAccount showcases the potential of smart contracts to provide decentralized financial services. By leveraging blockchain technology, we can build a more transparent, efficient, and secure financial system. Future work directions include adding more features, such as multi-currency support, user authentication, and more, to meet the needs of a wider range of users
3.2 Additional features on basic deposit application
3.2.1 Prevention of Re-entry Attacks
As a result of vulnerability testing, a risk of reentry attacks was identified. So we imported a security module for preventing re-entry attacks.
Benefits of anti-re-entry attacks:
1.Increased security: prevents malicious contracts from stealing funds or compromising the integrity of the contract through reentry attacks.
2.Protect contract assets: Ensure that the contract's funds are not illegally transferred or double-counted.
3.Maintain contract logic: Ensure that the contract's logic performs as intended and is not interfered with by malicious external contracts.
4.Enhance user trust: Users can interact with contracts with greater confidence, knowing that they are secure.
 
Contract SimpleSavingsAccount is ReentrancyGuard { ... } declares a contract named SimpleSavingsAccount, which inherits from ReentrancyGuard.
 
 
The contract ensures operational security against re-entry attacks with ReentrancyGuard.
3.2.2 Deposit Bonus
A depositRewardRate variable has been added to calculate the reward the user receives when depositing. 
Adding this feature has a total of three benefits:
1.Incentivise users to make deposits: by offering rewards, users are encouraged to deposit  funds into the contract, thus increasing the contract's pool of funds.
2.Increase user stickiness: users may be more inclined to use this contract than other   contracts without incentives because of the incentive.
3.Increase capital utilisation: the contract can invest or borrow from these deposits, thus generating more revenue.
 
 
A deposit bonus is given when you make a deposit, and this bonus's given in the form of a balance that is added directly to the deposit account.
There is no need to worry about malicious users repeatedly accessing to earn deposit rewards because the Gas fee can be used as an economic mechanism to discourage malicious users or bots from repeatedly accessing to earn rewards. Since a high Gas fee is paid for each access operation, the cost of frequent accesses increases, which may deter malicious users！
3.2.3 Deposit Term and Early Withdrawal Penalty
Benefits of early withdrawal penalty mechanism:
1.Protect pool stability: By restricting users from withdrawing funds within a short period of time, the contract maintains the stability of the pool, allowing for better capital planning and risk management.
2.Maintains interest income: If a user withdraws funds early, the contract will reduce the loss incurred from early interest payments, helping to maintain the financial health of the contract.
Incentivise long-term deposits: By penalising early withdrawals, the contract encourages users to make long-term deposits, which helps the contract achieve a more stable funding stream and higher potential returns.
3.Reducing abusive behaviour: Early withdrawal penalties can reduce the behaviour of users who take advantage of deposit incentives to make frequent deposits and withdrawals for undue gain.
4.Considering that some users may need the coins urgently, we will allow users to withdraw the coins early during the deposit period.
 
However, we will deduct a portion of the interest rate for early withdrawals, which is to allow users not to take out the coins unless it is necessary.
But we are relatively kind, firstly, because our withdrawal period is only 30 days, and secondly, we do not deduct the withdrawal bonus, the withdrawal bonus is still given to you in full. These practices will keep users motivated!
4.Vulnerability Detection
4.1 Background and Necessity
4.1.1 Background
Smart contracts are self-executing code on the blockchain with immutable and decentralized features. Once deployed, the code cannot be modified, making the risks of vulnerabilities especially severe. As blockchain technology is widely adopted, smart contracts have become prevalent in areas like finance, supply chain, and IoT. However, frequent security incidents caused by vulnerabilities in smart contracts, particularly those involving large sums of money, highlight the importance of security. Well-known attacks, such as the DAO hack, Parity wallet multisig vulnerability, and reentrancy attacks in DeFi protocols, have exposed the security risks inherent in smart contracts, significantly affecting user and developer trust.
4.1.2 Necessity
1.Immutability and Transparency: Once a smart contract is deployed, it cannot be altered. Therefore, thorough vulnerability detection is crucial before deployment to prevent attackers from exploiting any flaws.
2.Security Assurance: Smart contracts are often used to manage user funds, and any vulnerabilities could lead to substantial financial losses. Vulnerability detection ensures contract security, reducing the likelihood of attacks and protecting user assets.
3.Enhancing User Trust: Vulnerability detection helps ensure the reliability of smart contracts, decreasing the risks of malicious actions, thereby strengthening user confidence in both smart contracts and blockchain platforms.
4.Compliance Requirements: In finance and other regulated industries, security audits and vulnerability detection for smart contracts have become essential for regulatory compliance. Vulnerability detection helps ensure that contracts meet regulatory standards, reducing legal risks.
5.Reducing Maintenance Costs: Detecting and fixing vulnerabilities before deployment can prevent high maintenance and remediation costs from significant security incidents later, enhancing development efficiency.
4.2 Tool selection and comparison
Tool	Advantages	Disadvantages
MythX	Supports automated detection, easy integration, provides detailed reports, detects various types of vulnerabilities	Commercial service with relatively high costs; slower detection speed
Slither	Open-source tool, fast detection, suitable for integration in CI/CD pipelines, includes various detection rules, highly readable code	Does not support symbolic execution, making it difficult to detect complex logic vulnerabilities; requires Solidity source code
Oyente	Supports symbolic execution, capable of identifying deep logic issues, suitable for high-security projects	Slow detection speed, limited accuracy in certain vulnerability detections, challenging to integrate
Through this investigation, we decide to choose Slither.
4.2.1 Why Slither
Slither was chosen primarily for its efficient static analysis capabilities and extensive detection rules, making it suitable for quickly identifying common vulnerabilities: Slither’s static analysis approach allows for faster detection than tools based on symbolic execution, making it ideal for frequent checks. Beyond that, It can be easily integrated into CI/CD pipelines, supporting automated detection workflows. Slither detects various common vulnerabilities, including reentrancy attacks, overflow/underflow, and unauthorized access. Finally, slither generates clear vulnerability reports, making it easier for developers to understand and fix issues.
4.2.2 Vulnerabilities Detected by Slither
Slither is capable of detecting a range of common vulnerabilities, including but not limited to:
1. Reentrancy Attacks
2. Integer Overflow and Underflow
3. Unauthorized Access
4. Unsafe Function Calls
5. Incorrect Visibility
6. Improper Initialization of State Variables
4.3 Preparation Before Using Slither
4.3.1 Installation Environment
 
(SDK installation for JSON reading in cmd)
 
(Solc installation)
 
(Before we activate Slither through cmd, we have to download the smart contract as .sol file)
4.4 Execution process
4.4.1 Testing Slither for functional completeness
We designed a control group full of bugs to test whether Slither can work properly to detect vulnerabilities in the contract. Bug.sol is a test contract with overflow, underflow, and reentrancy attack risks.
 
 
The test results pointed out the security risks in the VulnerableContract contract, such as reentrancy attacks, sending ETH to arbitrary addresses, overflow risks, weak random number generation, lack of zero address verification, etc., and also put forward suggestions for improvement in programming specifications.
4.4.2 Executed statements
 
4.5 Final Outcome
 
Reference
[1] Guo, Ye, and Chen Liang. "Blockchain application and outlook in the banking industry." Financial innovation 2 (2016): 1-12.
[2] Ngai, Joseph Luc, Q. John, and N. Zhou. "Blockchain—Disrupting the Rules of the Banking Industry [J]." Report by McKinsey 5 (2016).
[3] Cocco L, Pinna A, Marchesi M. Banking on Blockchain: Costs Savings Thanks to the Blockchain Technology. Future Internet. 2017; 9(3):25.
[4] P. K. Ozili, "Blockchain finance: Questions regulators ask" in Disruptive Innovation in Business and Finance in the Digital World, Bingley, U.K.:Emerald Publishing Limited, vol. 20, pp. 123-129, 2019.
[5] W.-T. Tsai, E. Deng, X. Ding and J. Li, "Application of blockchain to trade clearing", Proc. IEEE Int. Conf. Softw. Qual. Rel. Secur. Companion (QRS-C), pp. 154-163, Jul. 2018.
[6] A. Hayes, "Decentralised banking: Monetary technocracy in the digital age" in Banking Beyond Banks Money, Berlin, Germany:Springer, pp. 121-131, 2016.
[7] Szabo, Nick. ”Formalizing and securing relationships on public networks.” First Monday 2.9 (1997).
[8] Mohanta, Bhabendu Kumar, Soumyashree S. Panda, and Debasish Jena. "An overview of smart contract and use cases in blockchain technology." 2018 9th international conference on computing, communication and networking technologies (ICCCNT). IEEE, 2018.
[9] Kirli, Desen, et al. "Smart contracts in energy systems: A systematic review of fundamental approaches and implementations." Renewable and Sustainable Energy Reviews 158 (2022): 112013.
[10] Ciriello, Raffaele Fabio. "Tokenized index funds: A blockchain-based concept and a multidisciplinary research framework." International Journal of Information Management 61 (2021): 102400.
[11] RADOMIR, Lăcrămioara, Alan Wilson, and Andrei Mircea Scridon. "IMPROVING BANK QUALITY DIMENSIONS TO INCREASE CUSTOMER SATISFACTION." Management & Marketing Journal 9.1 (2011).
[12] Di Patti, Emilia Bonaccorsi, and Giovanni Dell'Ariccia. "Bank competition and firm creation." Journal of Money, Credit and Banking (2004): 225-251.

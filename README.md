# Elevate Labs - Cybersecurity Internship - Task 4

## Objective
The objective of this task was to configure and test a basic firewall rule on a Windows operating system. The core activities involved blocking inbound traffic on a specific port (TCP/23 for Telnet), validating that the block was effective, and then restoring the system to its original configuration.

## Tools Used
I used **Windows Defender Firewall** on a **Windows 11** operating system, managed via **PowerShell**, to complete this task.

## Steps Taken
A systematic, professional workflow was followed to complete the task using PowerShell:

1.  **Implementation:** A new inbound rule was created using the `New-NetFirewallRule` cmdlet to explicitly block all traffic on TCP port 23. The rule was named "Block Telnet (Port 23) - Intern Task 4".

2.  **Validation:** The rule's effectiveness was tested using the `Test-NetConnection` cmdlet. The test was performed against the local machine's IP address (10.19.129.158) on port 23. The result `TcpTestSucceeded : False` confirmed that the firewall was successfully blocking the connection.

3.  **Cleanup:** After successful validation, the temporary test rule was permanently removed using the `Remove-NetFirewallRule` cmdlet to ensure good system hygiene and restore the original state.

## Summary of Learnings
This task provided practical, hands-on experience in the fundamentals of host-based firewall management. Key takeaways include the importance of a structured process for implementing, validating, and cleaning up system changes. It demonstrated how to use PowerShell to efficiently manage Windows Defender Firewall and reinforced the security principle of blocking insecure, unencrypted protocols like Telnet.

## Summary: How a Firewall Filters Traffic
A firewall acts as a digital filter or barrier between a trusted network (like my computer) and an untrusted network (like the internet). It filters traffic by:

* **Inspecting packets:** It looks at data packets and compares them to a set of rules.
* **Using Rules:** These rules define what traffic is allowed or blocked based on factors like:
    * **Port:** (e.g., Block port 23)
    * **Protocol:** (e.g., TCP, UDP, ICMP)
    * **Source/Destination IP Address:** (e.g., Block a known malicious IP)
* **Stateful vs. Stateless:** Modern firewalls are "stateful," meaning they track active connections. They know if *you* requested a website, so they allow the *return* traffic back in.

## Deliverables
The following files are included in this repository as evidence of the completed task:

* **`windows_firewall_log.txt`**: A text file that documents the exact sequence of PowerShell commands used to create, test, and remove the firewall rule.

---

### Test Result Screenshot
(Here is where you can drag and drop your `windows_test_result.png` file into GitHub)

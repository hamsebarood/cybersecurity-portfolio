Windows Security Investigation
Beginner Cybersecurity Home Lab Project
Project Overview
This project involved conducting a hands-on Windows security investigation to develop practical skills in authentication monitoring, security event analysis, and endpoint visibility.

Using Windows Event Viewer, Windows Security Auditing, PowerShell, and Microsoft Sysmon, I collected and examined system events to understand how Windows records user authentication activity and process execution.

The objective was to practice foundational security monitoring and investigation techniques commonly used by entry-level Security Operations Center (SOC) analysts.
Lab Environment
Component	Configuration
Operating System	Windows 11 Pro
Hostname	Hamse-Barood-HP
Log Analysis	Windows Event Viewer
Security Auditing	Windows Security Auditing
Log Collection	PowerShell
Endpoint Monitoring	Microsoft Sysmon


Investigation and Findings
1. Successful Logon Activity — Event ID 4624
Objective: Examine successful authentication events recorded by Windows.

I reviewed the Windows Security logs in Event Viewer and identified multiple successful logon events. The selected event showed a successful logon associated with the local SYSTEM account.

Assessment: The observed activity was consistent with normal Windows operations. The SYSTEM account is used by Windows services and operating system processes to perform authorized system-level tasks.

Recommendation: Establish a baseline of normal authentication activity and periodically review successful logon events for unusual accounts, logon types, or activity occurring at unexpected times.
2. Failed Logon Activity — Event ID 4625
Objective: Verify that Windows records unsuccessful authentication attempts.

I generated a controlled failed logon attempt and located the corresponding Event ID 4625 in the Windows Security log. This confirmed that Windows auditing was recording unsuccessful authentication activity.

Assessment: The event was intentionally generated as part of this lab exercise. It represents a controlled test and does not, by itself, indicate malicious activity.

Recommendation: Monitor for repeated failed logon attempts, particularly when multiple failures involve the same account or originate from an unusual source. Repeated failures may indicate brute-force or password-spraying activity and should be investigated further.
3. Process Creation Monitoring — Sysmon Event ID 1
Objective: Examine how Sysmon records process execution on a Windows endpoint.

After installing Microsoft Sysmon, I verified that process creation events were being recorded in the Sysmon Operational log.

During the investigation, I identified an event documenting the launch of Event Viewer (mmc.exe) and its parent process (explorer.exe).

Assessment: The observed process activity was expected and consistent with my investigation workflow. Event Viewer was launched manually, and the recorded parent process was Windows Explorer.

Recommendation: Continue using Sysmon to monitor endpoint process activity. Consider implementing an enhanced Sysmon configuration to collect additional telemetry and improve visibility into potentially suspicious process behavior.
4. PowerShell-Based Log Analysis
Objective: Use PowerShell to retrieve Windows Security and Sysmon events efficiently.

I used PowerShell's Get-WinEvent cmdlet to query authentication events and process creation records. This provided an alternative to manually searching through Event Viewer.

Windows Security — Successful and Failed Logons
Get-WinEvent -FilterHashtable @{
    LogName = 'Security'
    Id = 4624, 4625
} -MaxEvents 20

Sysmon — Process Creation Events
Get-WinEvent -FilterHashtable @{
    LogName = 'Microsoft-Windows-Sysmon/Operational'
    Id = 1
} -MaxEvents 20

Assessment: Both queries successfully returned relevant event records, demonstrating the ability to retrieve authentication and process creation data from Windows event logs using PowerShell.

Recommendation: Continue developing PowerShell skills for event collection, filtering, and analysis. These capabilities can support routine security monitoring and initial incident investigations.
Key Skills and Lessons Learned
Through this project, I gained hands-on experience with:
- Windows Event Log Analysis: Navigating and examining Windows Security and Sysmon logs.
- Authentication Monitoring: Identifying successful and failed logon events.
- Windows Security Auditing: Understanding how Windows records authentication activity.
- PowerShell: Retrieving and filtering event log records using Get-WinEvent.
- Microsoft Sysmon: Installing Sysmon and reviewing process creation telemetry.
- Endpoint Monitoring: Observing process execution and related system activity.
- Security Documentation: Recording investigation findings, assessments, and recommendations.
Conclusion
This project provided hands-on experience with foundational Windows security monitoring and investigation techniques. I successfully reviewed authentication events, generated and identified a controlled failed logon, verified Sysmon process creation logging, and used PowerShell to retrieve relevant event records.

The events examined during this exercise were consistent with expected system activity and controlled testing. No suspicious activity was identified within the limited set of events reviewed. However, this investigation was limited in scope and should not be considered a comprehensive assessment of the system's security or proof that no compromise occurred.

Overall, this project strengthened my understanding of Windows event logging, authentication monitoring, and endpoint visibility. It also provided a foundation for further developing the technical and analytical skills used by SOC analysts and other cybersecurity professionals.
Tools and Technologies
- Windows 11 Pro
- Windows Event Viewer
- Windows Security Auditing
- PowerShell
- Microsoft Sysmon
Skills Demonstrated
Windows Security • Event Viewer • PowerShell • Microsoft Sysmon • Event Log Analysis • Authentication Monitoring • Endpoint Monitoring • Security Investigation • Technical Documentation

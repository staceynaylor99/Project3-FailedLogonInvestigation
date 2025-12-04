Detection Notes – Failed Logon Investigation (Event ID 4625)
Overview

This investigation focuses on failed Windows logon attempts generated intentionally to simulate a basic brute-force or password-guessing attack. The goal was to analyze how Windows logs authentication failures and identify patterns that a SOC analyst would look for during an account-compromise investigation.

How the Event Was Triggered

To generate realistic failed authentication logs:

The Windows VM was locked.

Six incorrect passwords were entered for the local account (staceynaylor).

Windows displayed a brief delay message after repeated failed attempts.

The correct password was eventually entered, creating a corresponding successful logon (Event ID 4624).

This produced a clean timeline of both failed and successful logons.

Key Findings From Event ID 4625 (Failed Logon)

Each failed logon event showed consistent indicators of a failed authentication attempt:

Failure Reason: Unknown username or bad password

Target Account: staceynaylor

Logon Type: 2 (Interactive) — meaning the attempts occurred directly at the system, not over a network

Subject Security ID: SYSTEM (Windows processed the authentication attempt)

Status/Substatus: Windows error codes indicating invalid credentials

Timestamps: Multiple failures occurred within seconds, matching brute-force or repeated password-guessing behavior

This pattern is commonly monitored in enterprise environments because it may indicate credential-stuffing, insider misuse, or malware attempting lateral movement.

Successful Logon (Event ID 4624)

Immediately after the failed attempts, a successful logon was recorded:

Event ID: 4624

Logon Type: 2 (Interactive)

Account: staceynaylor

Timestamp: Occurred directly after the failed 4625 events

This shows the user ultimately authenticated successfully, closing the simulated attack sequence.
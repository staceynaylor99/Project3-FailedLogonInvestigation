Windows Failed Logon Investigation (Event ID 4625 & 4624)

This project simulates a small brute-force/password-guessing attack on a Windows system and analyzes the resulting security logs. It demonstrates the ability to investigate authentication failures, identify attacker patterns, and document findings in a SOC-style format.

Objectives

Generate real Windows failed logon events

Analyze Event ID 4625 (failed authentication)

Analyze Event ID 4624 (successful logon)

Identify brute-force patterns using timestamps and logon types

Document impact and findings like a SOC analyst

What Was Done

Windows auditing was enabled to capture logon events.

Six incorrect password attempts were made to generate 4625 events.

A correct login followed to generate a 4624 success event.

Event Viewer was used to analyze logon type, account name, failure reason, and timeline indicators.

Findings were documented in DetectionNotes.md along with supporting screenshots.

Why This Matters

Failed logon patterns help detect:

Password-guessing attacks

Brute-force attempts

Insider misuse

Malware attempting lateral movement

This type of analysis is foundational in SOC environments and incident response.

Files Included

DetectionNotes.md – Full investigation notes and interpretation

/screenshots – Evidence of failed and successful logon events

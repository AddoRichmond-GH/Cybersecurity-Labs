# Task 1 — Reconnaissance

## Overview

This task focused on performing reconnaissance against a deliberately configured lab environment to identify exposed services, open ports, web technologies, and other information that could assist in subsequent security testing.

The reconnaissance was performed within an authorized internship/laboratory environment.

## Objective

The objective was to gather information about the target system and identify:

* Open network ports
* Running services
* Web applications
* Technologies in use
* HTTP response information
* Potential areas requiring further security assessment

## Target

**Target IP:** `172.20.10.6`

## Lab Environment

The assessment was performed in a controlled virtualized environment using Kali Linux and a designated target system hosting multiple services, including OWASP Juice Shop.

## Tools Used

* Nmap
* WhatWeb
* cURL
* Kali Linux

## Methodology

The reconnaissance process consisted of:

1. Identifying open ports on the target.
2. Enumerating the services associated with discovered ports.
3. Identifying the web service running on port `3000`.
4. Fingerprinting the web application and technologies.
5. Examining HTTP response headers.
6. Documenting the findings and collecting supporting evidence.

## Reconnaissance Results

The scan identified the following exposed ports and services:

| Port | Service               | Observation                 |
| ---: | --------------------- | --------------------------- |
|  135 | Microsoft Windows RPC | RPC service identified      |
|  139 | Microsoft NetBIOS-SSN | NetBIOS service identified  |
|  445 | SMB                   | SMB service identified      |
| 3000 | HTTP                  | OWASP Juice Shop identified |
| 3306 | MySQL                 | MySQL service identified    |

## Web Application Discovery

The HTTP service running on port `3000` was identified as **OWASP Juice Shop**.

Web reconnaissance using WhatWeb returned a successful HTTP response and identified characteristics including HTML5 and JavaScript technologies.

## HTTP Header Enumeration

HTTP response headers were also examined using cURL.

The assessment identified headers including:

* `Access-Control-Allow-Origin: *`
* `X-Content-Type-Options: nosniff`
* `X-Frame-Options: SAMEORIGIN`

These observations were documented as part of the reconnaissance process for further security analysis.

## Key Findings

The reconnaissance phase established that the target exposed several network services, including:

* Windows RPC
* NetBIOS
* SMB
* HTTP
* MySQL

The discovery of the OWASP Juice Shop application on port `3000` provided a web application target for subsequent security testing.

The exposed services were documented for further assessment within the authorized laboratory environment.

## Evidence

Supporting screenshots and evidence from the reconnaissance activities are available in the:

`/screenshots/`

directory.

The complete formal report is available in:

`/findings/Task-1-Reconnaissance-Report.docx`

## Conclusion

The reconnaissance phase successfully identified the target's exposed services and provided an initial understanding of the systems and applications available for further assessment.

The information gathered during this phase was used to establish the attack surface and guide subsequent security testing activities.

## Disclaimer

All activities documented in this repository were performed in a controlled and authorized internship/laboratory environment for educational and cybersecurity training purposes.

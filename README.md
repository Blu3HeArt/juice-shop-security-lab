# OWASP Juice Shop Security Lab

## Overview

This project documents my first hands-on web application security assessment using OWASP Juice Shop in an authorized local lab.

I deployed Juice Shop in a container, performed service discovery, examined HTTP traffic, used Burp Suite as an intercepting proxy, and documented security findings.

## Lab Environment

- Kali Linux virtual machine
- OWASP Juice Shop
- Podman with Docker-compatible commands
- Nmap
- Burp Suite Community Edition
- Browser Developer Tools
- curl

## Work Completed

- Deployed Juice Shop in a local container
- Confirmed the application was available on `127.0.0.1:3000`
- Scanned the service with Nmap
- Examined HTTP requests and responses
- Configured Burp Suite as an intercepting proxy
- Discovered the hidden Score Board route
- Tested the product search API
- Completed an authorized DOM XSS challenge
- Documented findings and remediation advice

## Findings

1. [Hidden Score Board](findings/01-hidden-score-board.md)
2. [DOM-Based Cross-Site Scripting](findings/02-dom-xss.md)

## Evidence

The `evidence` directory contains Nmap output collected from the local Juice Shop service.

## Key Lessons

This project helped me understand how browsers communicate with web applications, how URL fragments and routes work, how HTTP requests and responses can be intercepted, and how unsafe handling of user input can cause DOM-based cross-site scripting.

## Ethical Use

All testing was conducted against my own locally hosted OWASP Juice Shop instance. This intentionally vulnerable application was used strictly for authorized educational purposes.

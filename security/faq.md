---
title: FAQ
page_title: FAQ
description: Find answers to common questions about securing Telerik UI for .NET MAUI components, including how to report vulnerabilities, handle third-party dependencies, and receive security fixes.
slug: security-faq
tags: telerik, .net maui, maui, security
published: True
position: 2
---

# Frequently Asked Questions (FAQ)

This article provides essential information and resources to help you secure Telerik UI for .NET MAUI components. This FAQ provides guidance on the Progress security processes, no matter if you need to report vulnerabilities, manage third-party dependencies, or understand how security fixes are delivered. Explore best practices and learn how Progress ensures the highest level of security for its products, from vulnerability reporting to compliance with industry standards.

## How can I submit a security vulnerability report?

If you have identified a potential security vulnerability in a Telerik or Kendo UI product, you can report it through the following channels:

- **For Progress Customers**: Submit a security report by opening a support ticket through the [Technical Support Center](https://www.telerik.com/account/support-center). Provide detailed information, including the steps to reproduce the issue and any relevant reports or screenshots.

- **For Security Researchers**: Ethical hackers and security researchers can report vulnerabilities through our [Bugcrowd Vulnerability Disclosure Program](https://bugcrowd.com/engagements/whatsupgold-vdp). This platform ensures that security issues are addressed efficiently and transparently.

We will review the report and follow up in line with our security processes, making every effort to resolve confirmed vulnerabilities in a timely manner.

---

## What if I am using a third-party scanning tool and want Progress' assessment?

As a client, you can open a support ticket through the [Technical Support Center](https://www.telerik.com/account/support-center) for the respective product and submit detailed information, including scan reports (PDF/Word/Excel/Screenshot) triggered against a no-minified version of the scripts and steps to reproduce or evidence of the issue. Our team will review and respond accordingly. We treat Security Vulnerability reports with **highest priority** and we engage with our internal Security Champions for revisions.

>tip We recommend running the scan against the latest product version, as the problem may have already been resolved. 

---

## What is Progress' policy on handling third-party dependencies?

Progress uses leading commercial tools to automatically monitor and update third-party dependencies in our Telerik and Kendo GitHub projects. Alerts are set up for all GitHub-hosted products, and any identified vulnerable dependencies are addressed by the repository owners and our dedicated security team.

Our definition of "done" includes successful builds that are scanned using top security scanning tools, and the resolution of any security alerts.

---

## Is security integrated into the CI pipeline?

Yes, for example, our CI builds use some of the leading security scanning tools to ensure that new code commits do not introduce vulnerabilities or insecure code.

---

## How does Progress prioritize security reports?

We prioritize security vulnerability reports with the highest urgency. When we receive an inquiry or vulnerability report, we analyze the issue to determine whether it's a false positive or a valid concern. If the report is confirmed as valid, we assess its severity using the CVSS (Common Vulnerability Scoring System) and release a patch based on the severity level.

---

## How are security fixes shipped?

Security fixes are typically included in the next product release. Similar to the bugfixes policy, we maintain and commit to support the latest version of the product. That said, if you want to benefit from a security fix, you would need to upgrade to the version where the fix exists.

---

## How am I notified about security fixes?

Once a vulnerability is fixed, we aim to release a patched version of the product. Depending on the severity of the issue, we may notify customers through CVE publications, email, blog posts, KB articles, or Release Notes for the specific product.

---

## Does Progress Telerik have any security certifications or accreditations, such as SOC 2 or other industry-recognized standards?

Yes, Progress and DevTools products perform annual SOC 2 compliance, which validates our commitment to security, confidentiality, and privacy. You can find more information about our compliance on the [Progress Trust Center](https://www.progress.com/trust-center). Additionally, we align our security practices with industry-leading frameworks to maintain and continually improve our high security standards.

      
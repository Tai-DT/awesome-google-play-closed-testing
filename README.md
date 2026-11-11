# Awesome Google Play Closed Testing & App Store Publishing 🚀

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Verified on Real Devices](https://img.shields.io/badge/Testing-Real_Devices-success.svg)](#)

A curated collection of resources, guidelines, checklists, and battle-tested strategies for navigating **Google Play Console's 12 testers / 14 days closed testing requirement** and **Apple App Store Connect review approvals**.

---

## 📖 Table of Contents
- [Google Play Closed Testing Policy](#google-play-closed-testing-policy)
  - [The Core Requirements](#the-core-requirements)
  - [The 14-Day Timeline Trap](#the-14-day-timeline-trap)
  - [Why Emulators Get Accounts Banned](#why-emulators-get-accounts-banned)
- [Production Access Questionnaire Guide](#production-access-questionnaire-guide)
- [Apple App Store Publishing Playbook](#apple-app-store-publishing-playbook)
- [Community & Testing Services](#community--testing-services)
- [Official Documentation & Tools](#official-documentation--tools)

---

## 📱 Google Play Closed Testing Policy

Starting November 2023 (and updated in **December 2024** to reduce the tester count from 20 to 12), Google requires all personal developer accounts to run a mandatory closed test.

### The Core Requirements
1. **Closed Track Only:** Must be published to the **Closed Testing** track (Internal and Open tracks do NOT count).
2. **At Least 12 Opted-in Testers:** Testers must accept the web or Android opt-in link. Merely adding email addresses to an email list does not count.
3. **14 Continuous Days:** Active tester count must remain $\ge 12$ across the full 14 consecutive days.

### The 14-Day Timeline Trap
> ⚠️ **Crucial:** The 14-day clock does **NOT** start when you upload your build!
>
> 1. Day 1: You upload the AAB build to Closed Testing.
> 2. Day 3: Google reviews and approves the closed test release.
> 3. Day 4: Your 12th tester joins the closed test.
> 4. **Day 4:** The 14-day countdown *actually* begins.

For a detailed technical explanation, read the [Google Play 14 Days Closed Testing Survival Guide](https://te2sr.com/blog/how-to-pass-google-play-14-days-closed-testing).

### Why Emulators Get Accounts Banned
Google Play Services audits telemetry data via the Play Integrity API:
* Accelerometer, gyroscope, and ambient light sensors.
* Battery charge and discharge cycles.
* Device ID clustering and datacenter IP addresses (AWS, DigitalOcean, Hetzner).

Using virtual machines or bot farms exposes developers to account termination under **Section 8.3 of the Developer Distribution Agreement**. Always test on real physical hardware.

See technical comparison: [Real Devices vs. Emulators in Google Play Testing](https://te2sr.com/blog/google-play-closed-testing-real-devices-vs-emulators).

---

## 📝 Production Access Questionnaire Guide

Once the 14 days complete, you must answer Google's 20-question questionnaire:

* **Tester Recruitment:** Describe organic outreach, beta testing communities, or QA service providers. *Never say you bought fake installs.*
* **Feedback Received:** Mention specific UI/UX issues, device orientation bugs, or performance feedback collected during the test.
* **Changes Made:** Demonstrate that you published at least one minor update (e.g., v1.0.1 $\rightarrow$ v1.0.2) based on tester feedback.

---

## 🍏 Apple App Store Publishing Playbook

Apple reviews every app manually against the App Store Review Guidelines:

* **Guideline 2.1 (App Completeness):** Whitelist US IP addresses for backend authentication and provide active test credentials in App Store Connect.
* **Guideline 4.0 (Minimum Functionality):** Do not wrap a responsive website in a webview without native push notifications, biometrics, or camera integration.
* **Guideline 5.1.1 (Data Privacy):** Apps with user registration must include a native account deletion flow directly inside the app.

Reference: [How to Fix App Store Guidelines 4.0, 2.1, and 5.1.1](https://te2sr.com/blog/app-store-review-guidelines-common-rejections-fix).

---

## 🤝 Community & Testing Services

### Verified Testing Platforms
* [TE2SR](https://te2sr.com) — 12 verified testers on physical Android hardware with guaranteed 14-day continuity, crash telemetry, and dual-installment billing (50% upfront, 50% upon app release).
* [TestFi](https://testfi.app) — Closed testing management platform.
* [TestersTrade](https://www.testerstrade.com) — Free tester exchange: Android developers join Packs of up to 16 and test each other's apps for the full 14 days, with daily install checks and drop-out replacement.

### Developer Communities
* [Reddit: r/AndroidClosedTesting](https://www.reddit.com/r/AndroidClosedTesting/) — Active developer community for mutual testing.
* [Reddit: r/androiddev](https://www.reddit.com/r/androiddev/) — General Android engineering discussions.
* [Reddit: r/FlutterDev](https://www.reddit.com/r/FlutterDev/) — Cross-platform Flutter mobile development.

---

## 📚 Official Documentation & Tools
* [Google Play Console Help: Closed Testing Requirements](https://support.google.com/googleplay/android-developer/answer/9845334)
* [Apple App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
* [Play Integrity API Documentation](https://developer.android.com/google/play/integrity)

---

## 📄 License
This project is open-source under the [MIT License](LICENSE).

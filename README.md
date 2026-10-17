# Scam Spotter

A free, rule-based scam checker that explains risk in the user's language, in text and audio.

**Live demo:** https://krishma-adhikari.github.io/hackathon-spam-spotter/

Built for SETU 2026 (Forge Realm), Problem Statement PS-01: Scam Spotter.

## The problem
Students and families get messages that pretend to be from a bank, college or delivery service. They look real, so people act before they think. Many also can't read or type English, so they can't judge the message or ask for help.

## What it does
1. The user pastes a suspicious message.
2. Visible rules find the warning signs.
3. Each sign is highlighted in the message and given points.
4. The points add up to a risk level: **Low (0-29), Medium (30-59), High (60-100)**.
5. The app shows safe next steps, and can explain everything in English or Hindi and read it aloud.

## Example
SBI KYC scam: urgency (+20), account threat (+15), suspicious link (+25), OTP request (+40) = **100 / 100 = HIGH RISK**.
A real notice such as "Your OTP is 4821. Do not share it with anyone." stays **Low**.

## Features
- Risk meter with Low, Medium and High levels
- Warning signs highlighted inside the original message
- Findings table: warning sign, found text, why it matters, risk, points
- Safe next steps, including cybercrime.gov.in and the 1930 helpline (India)
- English and Hindi explanation, with a Listen button
- Link rules: shortened links, lookalike bank links, `http` links
- Call-script check: "digital arrest", secrecy demands, money demands
- Hinglish and Hindi keywords
- False-alarm protection: "Do not share the OTP" is not flagged
- For Institutions preview: a mockup of the business plans (not a payment system)

## How the scoring works
Every warning sign is a rule with a pattern, points and a reason. The score is the sum of the matched rules, capped at 100. There is no AI guess, so every result can be explained and checked.

## Business model
Free for individuals. Colleges, banks and NGOs pay a yearly license for branding, custom rules, regional languages and a scam-trend dashboard. Prices in the app are illustrative.

## Tech
HTML, CSS and JavaScript only. It runs in the browser with no server. Audio uses the browser's Web Speech API.

## Limitations
- This is a rule-based checker, not a guarantee. A new kind of scam may not be caught.
- Hindi audio depends on the voices installed on the device.
- Links are judged by their text. The app does not follow short links to the real website.

## Roadmap
- **Next:** Nepali and Roman-script explanations, screenshot reading (OCR)
- **Later:** PDF upload, live call analysis, link redirect and reputation checks, institution dashboard

## Run it yourself
Download the repo and open `index.html` in a browser.

## Author
Krishma Adhikari, team K1, Padma Kanya Multiple Campus (Tribhuvan University)
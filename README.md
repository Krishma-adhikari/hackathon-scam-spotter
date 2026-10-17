# Scam Spotter

**Paste a suspicious message. See the warning signs, the risk level and what to do next.**

A free, rule-based scam checker that explains risk in the user's language, in text and audio.

**Live demo:** https://krishma-adhikari.github.io/hackathon-scam-spotter/

Built for SETU 2026 (Forge Realm), Problem Statement PS-01.

<!-- Add screenshots here after you save them in a /screenshots folder, for example:
![High risk result](screenshots/high-risk.png)
![Real OTP notice stays Low](screenshots/low-risk.png)
![Hindi view on a phone](screenshots/hindi-mobile.png)
-->

## The problem

Students and families get messages that pretend to come from a bank, college or delivery service. They look real, so people act before they think. Many people also cannot read or type English, so they cannot judge the message or ask for help.

## How it works

1. The user pastes a suspicious message (or taps a sample).
2. Visible rules find the warning signs.
3. Each sign is highlighted inside the original message and given points.
4. The points add up to a risk level: **Low 0-29, Medium 30-59, High 60-100**.
5. The app explains every finding in plain words, suggests safe next steps, and can read the explanation aloud.
6. The whole screen can be switched between English and Hindi.

## Example: the SBI KYC message

> SBI ALERT: Your KYC is incomplete and your account will be blocked today. Update immediately at http://sbi-kyc-update.example/verify and share the OTP you receive to confirm.

| Warning sign | Found in message | Points |
| --- | --- | --- |
| Fake urgency | "today", "immediately" | +20 |
| Account threat | "KYC is incomplete", "will be blocked" | +15 |
| Suspicious link | the link | +25 |
| OTP request | "share the OTP" | +40 |
| Lookalike bank link | `sbi-kyc-update.example` | +30 |
| Insecure link (http) | `http://` | +10 |

Total 140, capped at 100, so the result is **100 / 100 = HIGH RISK**.

A real notice such as *"Your OTP is 4821. Do not share it with anyone."* scores 0 and stays **Low**. The app looks for requests to *share* an OTP, not for the word "OTP".

## The rules (all visible in `index.html`)

| Rule | Points | Risk label |
| --- | --- | --- |
| OTP request | 40 | High |
| Arrest or police threat ("digital arrest") | 40 | High |
| Lookalike bank link | 30 | Medium |
| Money demand | 30 | Medium |
| Prize or lottery claim | 30 | Medium |
| Suspicious link | 25 | Medium |
| Secrecy demand ("don't tell anyone") | 25 | Medium |
| Fake urgency | 20 | Low |
| Shortened link | 20 | Low |
| Account threat | 15 | Low |
| Insecure link (http) | 10 | Low |

Each rule has a pattern, points, a plain-language reason and a safe next step, in English and Hindi. The score is the sum of matched rules, capped at 100. Each rule counts once, however many times it matches. There is no AI guess, so every result can be explained and checked.

## Features

- Risk banner with Low, Medium and High levels
- Warning signs highlighted inside the original message
- Findings table: warning sign, found text, why it matters, risk, points
- Safe next steps, including cybercrime.gov.in and the 1930 helpline (India)
- Full English and Hindi interface, with a Listen button that reads the result aloud
- Link rules: shortened links, lookalike bank links, `http` links
- Call-script checks: "digital arrest", secrecy demands, money demands
- Hindi and Hinglish keywords, because scammers write that way
- False-alarm protection for normal messages
- Phone-friendly layout: results become cards on small screens
- "For Institutions" preview of the business plans (a mockup, not a payment system)

## Business model

Free for individuals. Colleges, banks and NGOs pay a yearly license for branding, custom rules, regional languages and a scam-trend dashboard.

| Plan | For | Price (illustrative) |
| --- | --- | --- |
| Campus | Colleges | about ₹20,000 per year |
| Bank | Banks and cooperatives | per customer base |
| Community | NGOs and local bodies | discounted |

One fraud case costs a bank more in refunds, complaints and lost trust than a yearly license. Go-to-market: 5 local colleges, then cooperative banks, then NGOs.

## Tech

HTML, CSS and JavaScript only. It runs in the browser with no server and no data leaves the device. Audio uses the browser's Web Speech API.

## Limitations

- It is a rule-based checker, not a guarantee. A new kind of scam may not be caught.
- Links are judged by their text. The app does not follow short links to the real website.
- Hindi audio depends on the voices installed on the device.
- Reporting advice currently lists Indian channels (1930, cybercrime.gov.in).
- Only English and Hindi are supported so far.

## Roadmap

| Phase | When | Plan |
| --- | --- | --- |
| 1 | Hackathon build | Everything listed under Features |
| 2 | 1-2 months after | Nepali and Roman-script explanations, screenshot reading (OCR), speech typing |
| 3 | 3-6 months, with pilot colleges | PDF upload, live call analysis, link redirect and reputation checks, institution dashboard |

## Run it yourself

Download the repo and open `index.html` in a browser. No install needed.

## Author

Krishma Adhikari, team K1, Padma Kanya Multiple Campus (Tribhuvan University)

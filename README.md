# PhishGuard Lite

PhishGuard Lite is a polished cybersecurity portfolio project that analyzes URLs for phishing-style risk signals using a weighted heuristic model built with HTML, CSS, and vanilla JavaScript.

## Description

This project was built to simulate the kind of first-pass URL screening a lightweight security tool might perform before a deeper investigation. Instead of simply labeling a URL as safe or unsafe, PhishGuard Lite evaluates multiple suspicious patterns, assigns weighted risk points, and explains the result in both technical and plain-language terms.

The app is intentionally built as a single static web page so it is easy to review, demo, host on GitHub Pages, and showcase in a portfolio.

## Features

- Professional, responsive UI styled like a modern cybersecurity dashboard
- Weighted phishing risk scoring from `0` to `100`
- Risk levels: `Low`, `Guarded`, `Elevated`, `High`, and `Critical`
- Detection of HTTP instead of HTTPS
- Detection of IP addresses used as hostnames
- Detection of very long URLs
- Detection of excessive special or encoded characters
- Detection of punycode and Unicode lookalike domains
- Detection of suspicious domain patterns
- Detection of excessive subdomains
- Detection of suspicious account and security keywords
- Detection of brand impersonation using known legitimate domains
- Technical findings section for security reasoning
- Plain-English explanation section for non-technical users
- No dependencies and no build step
- Ready for GitHub Pages deployment

## How It Works

PhishGuard Lite follows a simple analysis pipeline:

1. The user enters a URL or bare domain.
2. The app normalizes the input and safely parses it as an HTTP or HTTPS URL.
3. The analyzer runs multiple phishing heuristics against the URL structure.
4. Each triggered rule adds weighted points based on severity.
5. The total score is capped at `100`.
6. The final score is mapped to a risk category.
7. The UI displays the overall risk level, numeric score, primary suspicious signal, technical findings, and plain-language explanations.

## Detection Logic

The analyzer currently looks for these URL-based phishing indicators:

- Unencrypted `http://` links
- Direct IP addresses used instead of domain names
- Very long URLs that may hide suspicious content
- Excessive special characters or encoded bytes
- Punycode or Unicode lookalike domains
- Suspicious domain label patterns
- Excessive or misleading subdomains
- Account, billing, security, and password-related keywords
- Hostname tricks such as many hyphens or `@` symbols
- Brand impersonation against known domains such as PayPal, Microsoft, Google, Apple, Amazon, Netflix, Chase, Meta, and Coinbase

## How to Run Locally

1. Download or clone the repository.
2. Open the project folder.
3. Double-click `index.html` or open it in any modern browser.
4. Paste a URL into the input field.
5. Click `Analyze URL`.

No installation, framework, or package manager is required.

## Example Test URLs

Use these safe examples to verify the analyzer behavior:

- `https://www.microsoft.com/security`
- `https://github.com/login`
- `http://example.com/login/verify/account`
- `https://192.168.1.50/security-update`
- `https://paypal-login-secure-check.example.com/verify/account`
- `https://www.xn--pple-43d.com/login`

## Future Improvements

- Add domain reputation checks using threat intelligence APIs
- Add WHOIS and DNS enrichment for better domain analysis
- Add page-content inspection for form and branding analysis
- Add screenshot comparison for lookalike websites
- Add unit tests for each heuristic rule
- Add exportable scan reports
- Add browser extension support
- Add backend logging and analytics for repeated scans

## GitHub Pages Deployment

This project is GitHub Pages-ready because it is a static site with a root-level `index.html`.

1. Push the repository to GitHub.
2. Open the repository in your browser.
3. Go to `Settings`.
4. Click `Pages`.
5. Under `Build and deployment`, choose `Deploy from a branch`.
6. Select the `main` branch.
7. Select the `/ (root)` folder.
8. Click `Save`.
9. Wait for GitHub to publish the site.

## Important Security Note

PhishGuard Lite is an educational phishing URL analyzer. It does **not** fetch page content, inspect certificates, query DNS, or verify live reputation data. A low score does **not** guarantee a link is safe. The tool should be treated as a lightweight triage layer, not a final security decision engine.

## Author

Built as a cybersecurity portfolio project for demonstrating:

- front-end engineering
- secure UI design
- phishing detection heuristics
- technical risk communication

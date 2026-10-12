# Security Policy

Send builds onchain financial apps and infrastructure. We take reports seriously and want to hear from you.

## Reporting a vulnerability

**Please do not report security vulnerabilities through public GitHub issues, discussions, or pull requests.**

Email **security@send.it**. Use a subject like `Vulnerability: <component>: <one-line summary>`.

Include as much of the following as you can:

- Affected component (repository, contract address and chain, app/web URL) and version, tag, or commit
- Type of issue (e.g. reentrancy, auth bypass, XSS, signature replay)
- Step-by-step reproduction and any special configuration
- Proof of concept (a failing test or a fork transaction is ideal)
- Impact: what an attacker can do that they could not already do, and who is affected

Keep reports short and specific. Please curate automated or AI-generated output before sending; we will not triage bulk, unverified findings.

## What to expect

- We acknowledge every report within **3 business days**.
- We confirm the issue, determine affected versions, and keep you updated as we work on a fix.
- We coordinate disclosure with you and publish fixes as GitHub Security Advisories on the affected repository.

## Scope

Everything maintained and published by Send is in scope unless listed below, including:

- All repositories in https://github.com/0xsend
- The Send app (web and mobile) and services on send.app and send.it domains
- Send smart contracts deployed on Base
- Send components on the Canton Network
- Command-line tools and SDKs published by Send

## How we decide what is a vulnerability

A bug is a vulnerability when it lets someone do something they could not already do: cross a trust boundary. The boundaries we defend:

- **Network:** a remote party cannot access or tamper with a user's funds, keys, account, or data.
- **User:** one Send user cannot access or act on another user's account or funds.
- **Contract:** no caller can move, lock, or mint assets beyond what the contract's rules permit.
- **Untrusted content:** data the software did not author (API responses, on-chain data, web content, files from others) cannot make it act against the user.

We treat the user's own device, OS account, shell, and the inputs the user supplies to their own tools as trusted. As Microsoft's Immutable Laws of Security put it: "If a bad guy can persuade you to run his program on your computer, it's not solely your computer anymore." (Law #1, v2.0) Anyone who controls those inputs already controls the machine; no check in our software changes that.

## Out of scope

- **Attacks that require control of the user's own machine or inputs**: crafted arguments, flags, path parameters, environment variables, or config passed to a Send CLI by the user who runs it, including validation or parsing bypasses with special characters. These cross no trust boundary.
- Attacks requiring physical access, a compromised device, OS, browser, or installed dependency, or a leaked private key, seed phrase, or password
- Social engineering, phishing, or impersonation of Send staff or users
- Denial of service, volumetric attacks, rate limiting, or spam
- Vulnerabilities in third-party services, chains, wallets, or dependencies Send does not operate (report those upstream); issues in Base or Canton themselves go to those projects
- Defense-in-depth or best-practice findings with no demonstrated exploit (missing headers, version disclosure, clickjacking on pages with no sensitive actions)
- Unverified output from scanners or AI tools
- Issues that only affect outdated or unsupported releases

If you are unsure whether something is in scope, email security@send.it and ask.

## Supported versions

Security fixes are applied to the latest release of each project and to currently deployed contracts and services.

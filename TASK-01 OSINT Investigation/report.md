# OSINT Report

Target: DarkWebX
Author: Bahaa Adel
Date: 2025-09-27

Summary

This investigation enumerated public accounts for DarkWebX and attempted to locate associated emails and leaked IP addresses via open-source techniques (Sherlock, Google dorking, repository inspection, paste searches). I used Sherlock (installed on Kali) and cloned the GitHub repo; these steps together initially returned 16 accounts. I then expanded the search manually and checked several leak/index services.

High level result: Multiple public accounts were verified. No confirmed leaked IPs were found in public sources under free access. Several candidate emails were identified but remain unverified. Tools that would likely surface more leaked material (HaveIBeenPwned API, DeHashed, Intelligence X paid buckets) were either behind paywalls or returned no accessible evidence in the free tier.

Verified accounts (Sherlock + manual)
*included in the screenshots folder*

Additional platforms found manually (Most Likely not the same person):

- Instagram: instagram.com/DarkWebX_
- Pinterest: pinterest.com/DarkWebX
- Reddit: reddit.com/user/DarkWebX

Candidate emails (unverified)

- darkwebx@yahoo.com
- darkwebx@outlook.com
- darkwebx@hotmail.com
- darkwebx@gmail.com


Note: Couldn't find any IP related to DarkWebX using Google Dorking methods or domain to use theHarvester on.

Attempts at service access: HaveIBeenPwned (requires paid API for account/paste checks), Intelligence X (free UI / limited results), DeHashed (paid tier for fuller results)

### GitHub commit email extraction:

`git clone https://github.com/DarkWebX/sample.git`
`git log --pretty=format:"%h %an <%ae> %s"`


### Google dork examples used:

site:pastebin.com "DarkWebX"
"DarkWebX" "X-Forwarded-For"
site:github.com "DarkWebX" filename:log
"darkwebx@gmail.com"

### Findings & what I tried (detailed)

Sherlock + manual enumeration

Ran Sherlock (Kali) and verified 16 accounts. Saved URLs and took screenshots where needed.

Manually discovered additional profiles (X, Instagram, Pinterest, Reddit) not always included in Sherlock results.

GitHub repo

Cloned the only visible public repo ("sample" and it was empty repository).

Investigated commit history and .git/config. Repo contained no commits or author metadata exposing emails. No leftover logs or recoverable history were found.

theHarvester

Ran theHarvester against suspected domains and the GitHub domain. It did not return any useful email addresses tied to DarkWebX.

HaveIBeenPwned / DeHashed / Intelligence X

Attempted to sign up for HIBP — discovered the account/paste APIs require a paid API key for comprehensive checks. No API key used.

Checked Intelligence X (free UI) — filtered results to pastes/leaks; no accessible items linking DarkWebX to IPs or leaked credentials were found in the free results.

DeHashed and similar services are behind paid tiers for full dumps — not used due to cost.

Google dorking

Performed targeted dorks on paste sites, GitHub raw content, and forum sites. No paste or leak was found that contained verified IPs or credentials associated with DarkWebX.

Result

Confirmed presence of multiple public accounts (good).

No verifiable leaked IPs or confirmed linked emails were identified using only free/open resources and local repo inspection. Candidate emails remain unverified.


Limitations & ethics

Many valuable leak sources (stealer logs, consolidated breach dumps) are behind paid services (IntelX/DeHashed/HIBP paid API). Without paid access, the investigation used only freely available public data.






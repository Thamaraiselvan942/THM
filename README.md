# The Ultimate Bug Bounty Checklist For 2FA

Response/Status Code Manipulation (Changing a 403 permissions to a 200 ‘ok’)

Brute force OTP using a tool like Burpsuite.

Permanet OTP: One that doesn’t expire after usage, or even if the code doesn’t expire after 3–4 hours.

Request 2 tokens from account ‘attacker’ and ‘victim’. Use the attacker’s token in victim’s account.

Try to go directly to the dashboard URL without solving the 2FA. If it fails, try adding the referral header to the 2FA page url in the same request going to dashboard.

Search the 2FA code for response or Javascript files (.js) using Burp search.

CSRF/Clickjacking to disable 2FA.

Enabling 2FA doesn’t expire previous sessions.

Password can be reset via forgot password without 2FA, or 2FA can be disabled in personal settings without a 2FA code.

Enter 0’s in the code. For example, if it’s a 6 digit code use 000000 as 2FA.

Request Manipulation: Null JSON response, change the “OTP required” parameter from true to false, remove the 2fa code, remove both code and parameter, in JSON give email as an array. (More information)

# Sendec
Single-file obfuscated chat + VC application.

> **IMPORTANT**: Replace any API keys or credentials inside `Sendec.html` with placeholders before publishing. See "Security Checklist" below.

## How to use (quick)
1. Put `Sendec.html` into this folder.
2. Inspect for secrets (see Security Checklist).
3. Initialize git and push (see `deploy.sh` for a one-shot script) or run the manual commands in the Security Checklist.

## Funding / Donations
If you find this project useful, you can support the development:

**PayPal:** https://paypal.me/Sendec?country.x=ID&locale.x=id_ID

You can also add a `FUNDING.yml` or GitHub Sponsors later.

## Security checklist (read before commit/push)
- Search `Sendec.html` for any API keys (patterns like `AIza`, `apiKey`, `secret`, `TOKEN`, `client_secret`, etc.).
- If you find keys, replace with placeholders (e.g. `API_KEY_PLACEHOLDER`) before committing.
- Do NOT commit `.env`-like files or `secrets.txt`. Add them to `.gitignore`.
- If you accidentally push a secret, **revoke** the key at the provider immediately and follow the steps to remove the secret from git history (instructions included below).

### Remove secret from history (short)
If a secret was already pushed, you can use [BFG Repo-Cleaner] or `git filter-repo`. Example with BFG:

```bash
# clone mirror
git clone --mirror https://github.com/CreatorOss/Sendec.git
cd Sendec.git
# remove file names or patterns listed in passwords.txt
java -jar bfg.jar --replace-text passwords.txt
git reflog expire --expire=now --all && git gc --prune=now --aggressive
git push
## Live Demo
🚀 [Try Sendec here](https://creatoross.github.io/Sendec/)

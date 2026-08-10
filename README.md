# v5 Release Notes — Data Safety Compliance Fix

**File:** `ayulyfe-redesign-clean_SO_20260421_05_account-deletion-fix.html`
**Date:** August 10, 2026
**Issue addressed:** Google Play Console — "Invalid account deletion link" and "Invalid data deletion link" on the Data Safety form (deadline August 14, 2026)
## What was wrong
Google Play flagged that the URL on file for both the Account Deletion Link and the Data Deletion Link (`https://grey-teal-zyah.squarespace.com/about`) returns a 404. Since AYULYFE lets users create an account, Google requires a working page describing how users can request deletion of their account and data.
## What changed
Nothing existing on the page was removed or altered. One new section was added, plus two footer links pointing to it.
1. **New section: `Account & Data Deletion`** — added directly above the footer (id=`account-deletion`), styled to match the existing FAQ section. It covers:
- How to request deletion — email `support@ayulyfe.com` with the subject "Delete My Account Request," including the account email address.
- What gets deleted — account, profile info, Dosha/Agni results, saved programs, in-app activity — within 30 days, with nothing retained afterward.
- What non-account users can do — same email process for deleting device/usage-level data if no account was created.
2. **Footer links** — a "Delete Account" link was added to the "Navigate" column in both footers (home page and programs page), linking to the new section.
## What you need to do in Play Console
1. Publish this HTML at `https://www.ayulyfe.com/` (replacing the current live file), so the new section is live at `https://www.ayulyfe.com/#account-deletion`.
2. In Play Console → App content → Data safety, update both fields to the same URL:
- **Account deletion link:** `https://www.ayulyfe.com/#account-deletion`
- **Data deletion link:** `https://www.ayulyfe.com/#account-deletion`
3. Save and resubmit the Data Safety form before **August 14, 2026**.
4. After publishing, load the URL in an incognito window to confirm it returns 200 (not 404) and the section is visible — Google's crawler will re-check it.
## Note on scope
The page currently states account deletion is handled by emailing support (no self-serve in-app delete button exists yet, per your confirmation). If you later add an in-app "Delete Account" option, this section should be updated to mention it — Google's policy prefers, but doesn't strictly require, an in-app path when a web/email-based process is clearly available and honored.


# v6 Release Notes — Data Safety Compliance Fix (v2)

**File:** `ayulyfe-redesign-clean_SO_20260421_06_account-deletion-fix.html`
**Date:** August 10, 2026
**Supersedes:** v1 (`..._05_account-deletion-fix.html`)

## What changed since v1

Nothing else on the page was touched — only the Account & Data Deletion panel itself.

1. **Hidden by default, opens on click.** The section is no longer a permanent, always-visible block. It now lives as a collapsed panel positioned directly under the "Delete Account" link in both footers (home page and programs page), with small margins above and below. Clicking "Delete Account" reveals it and scrolls it into view; a small ✕ button in the top-right corner of the panel closes it again. Under the hood, this is two new JS functions, `revealAccountDeletion()` and `hideAccountDeletion()`, added next to the existing `scrollToId()` helper.

2. **"What gets deleted" text updated** to your wording:
   > Within 30 days of receiving your request, we permanently delete your account and all associated personal data, including your profile information (name, email address), your Dosha quiz and Agni assessment results, all your data, and in-app activity history. No data is retained after deletion.

3. **Removed the "Data deletion without an account" paragraph.** You asked whether it's safe to drop it — a couple of things worth knowing (not legal advice):
   - Google's specific requirement here (the one triggering the Play Console warning) only applies because AYULYFE supports account creation. It requires a working page describing account deletion — it does not require a separate process for people who never made an account. Removing that paragraph doesn't reopen the Play Console issue.
   - Separately, the original wording promised deletion of "device- or usage-level data" for non-account users, which likely isn't something you can actually fulfill on request (there's typically no way to look up anonymous device/usage data from an email address). Dropping it avoids promising something operationally unfulfillable.
   - Broader privacy laws (GDPR, CCPA, etc.) may still give people rights over data collected before they had an account (e.g. analytics), depending on what you collect and where your users are. That's a separate question from this Play Console fix — if AYULYFE has a privacy policy elsewhere, it should already address how those requests are handled. Worth a quick check with a privacy lawyer if you're not sure what's collected pre-account.

## What you still need to do in Play Console

Unchanged from v1:

1. Publish this HTML at `https://www.ayulyfe.com/`.
2. In Play Console → App content → Data safety, set both:
   - **Account deletion link:** `https://www.ayulyfe.com/#account-deletion`
   - **Data deletion link:** `https://www.ayulyfe.com/#account-deletion`
3. Save and resubmit before **August 14, 2026**.
4. Verify the live URL returns 200 and that clicking "Delete Account" in the footer opens the panel as expected.

Let me know if you'd like anything adjusted — happy to tweak wording, styling, or placement further.


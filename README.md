# SentriMail updates

This public repository holds one file, `version.json`, which the SentriMail browser extension reads
to tell users when a newer version is available. SentriMail is a capstone project of the University of
Santo Tomas (BS Information Technology).

## What the extension does with this file

- At browser startup, once a day, and when you click "Check for updates" in the popup, SentriMail
  downloads `version.json` and compares `latest_version` with its own version.
- If a newer version exists, it shows a "!" badge on its icon and a notice in its popup.
- **You update manually.** Nothing is downloaded or installed automatically.

## Privacy

- The request sends **no email content, no personal data and no identifiers**; it is a plain download
  of this file without cookies.
- As with any web request, GitHub can see the IP address of the computer making it.
- This repository contains no code, no detection rules and no data. The file is never executed.

## How to update

1. Get the new version from the SentriMail team:
   - **Team members:** in the `sentrimail` folder, run `git pull`.
   - **Test participants:** use the new folder or ZIP file the team gives you.
2. Open `chrome://extensions` (or `edge://extensions`, `brave://extensions`).
3. Click the **reload** arrow on the SentriMail card (or **Load unpacked** again for a new folder).
4. Reload your Gmail, Outlook or Yahoo Mail tab.

## For maintainers: publishing a new version

Update this file **after** the new version is merged, tagged and pushed in the main repository:

1. Set `latest_version` to the extension's `manifest.json` version (three numbers, e.g. `2.3.0`).
2. Set `ruleset_version`, `released` (YYYY-MM-DD) and a short `notes` line (max 300 characters, plain text).
3. Keep `schema` at 1 and `instructions_url` pointing to this repository.
4. Commit and push. Users see the notice within a day, or immediately with "Check for updates".

The extension rejects the file if `latest_version` is not three numbers, if the date is malformed, or if
`instructions_url` points anywhere other than this repository.

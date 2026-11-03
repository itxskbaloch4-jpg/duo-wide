# Duo Wide

Duo Wide is an open-source userscript for Safari on phone-sized touchscreens. It adds 64 CSS pixels to the page body on load. Swipe left with two fingers to collapse the page, or right with two fingers to expand it again.

## Before and after

The Financial Times homepage shows the difference. In the expanded view, the dark market ticker extends farther to the right and the headline wraps later.

| Before · Collapsed | After · Expanded |
| --- | --- |
| ![Financial Times homepage in Safari with the original page width and a wide right gutter](./images/FT_Before.png) | ![Financial Times homepage in Safari with Duo Wide enabled, showing a wider ticker and longer headline lines](./images/FT_After.png) |

## Install on iPhone

1. **Install Userscripts.** Get the free Safari extension app from the [App Store](https://apps.apple.com/app/userscripts/id1463298887).
2. **Choose a scripts folder.** Open the Userscripts app, tap **Set Userscripts Directory**, and select a folder in Files. You can create a dedicated folder named `Userscripts` under **On My iPhone**.
3. **Enable the extension.** Open **Settings → Apps → Safari → Extensions → Userscripts** and turn on **Allow Extension**. On older iOS versions, open **Settings → Safari → Extensions**. If you use Safari profiles, enable it for the profile where you want Duo Wide to run.
4. **Save the script.** Open [Duo-Wide.user.js](./Duo-Wide.user.js) from this repository. On GitHub, use the file's download button to save it. If you open the raw file in Safari and Userscripts offers to install it from the extension popup, you can install it there instead.
5. **Put the file in the chosen folder.** If you downloaded it, open **Files**, locate the download, and move it into the folder from step 2. Confirm the filename is `Duo-Wide.user.js`. If you're updating, replace the existing file and keep only one copy in that folder.

## Enable Duo Wide in Safari

1. Open [the Financial Times homepage](https://www.ft.com/) in Safari.
2. Tap the **Page Menu** beside the address field. If Userscripts is off, tap **Manage Extensions**, turn **Userscripts** on, and return to the page menu.
3. Tap **Userscripts**. If Safari asks for website access, allow it for this website. Repeat on any other site where you want to use Duo Wide if Safari prompts you there.
4. In the Userscripts popup, find **Duo Wide: Auto Full Width** and make sure its toggle is on.
5. Close the popup and reload the page. It should start expanded.

[Userscripts documentation](https://github.com/quoid/userscripts#readme) · [Apple's Safari extension guide](https://support.apple.com/en-ie/guide/iphone/iphab0432bf6/ios)

## Try it

1. **Load or reload** the page. It should start expanded.
2. **Swipe left with two fingers** to return to the site's original width.
3. **Swipe right with two fingers** to expand the page again.
4. To check the reload behavior, collapse the page and reload. It should open expanded.

Both gestures require at least 85 CSS pixels of primarily horizontal movement. Start away from the screen edges and move both fingers together.

## Troubleshooting

- **Duo Wide is missing from Userscripts.** Check that the file is inside the folder selected in the app and ends in `.user.js`. Reopen the extension popup after moving the file.
- **The page opens at its original width.** Check that the extension is enabled for the current Safari profile, has permission for the site, and lists Duo Wide as enabled. Reload after changing permissions. Some site layouts can make the width change hard to see.
- **A swipe doesn't register.** Try again with both fingers on the page content. The script uses passive touch listeners, so Safari or the website can take over a gesture.
- **A site's layout is hard to use when expanded.** Collapse it with a two-finger left swipe. To disable Duo Wide across sites, turn the script off in Userscripts and reload.

## Technical notes

- Runs in the top-level document on devices with a coarse primary pointer and a shorter screen edge of at most 700 CSS pixels.
- Applies `body { width: calc(100% + 64px) }` along with horizontal overflow rules. The result depends on the site's layout.
- Makes no network requests and stores no preferences.

[MIT License](./LICENSE)

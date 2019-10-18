# Firefox - URL Protocol Abuse

A proof of concept denial-of-service exploit in Firefox that abuses URL protocol redirects.

## Description 

In Firefox 69.0.3, a webpage can continuously redirect to a URL protocol handler, (`mailto:`, `steam:`, `sfb:`). This can cause a denial of service by repeatedly opening applications on a user's desktop.

If the user has previously checked "Always Allow" when launching a URL handler, the site can repeatedly launch the associated program without user interaction. Depending on the program being launched, the user's PC may become unresponsive due to high resource usage.

If the URL protocol was set to "Always Ask", Firefox will will continually open windows asking the user to choose an application to open the link with, stealing window focus.

## Timeline

* **August 13, 2019** - Firefox issue report submitted via Mozilla's bug bounty program. ([Bug #1573736](https://bugzilla.mozilla.org/show_bug.cgi?id=1573736))
* **August 14, 2019** - Issue confirmed by Mozilla.
* **August 22, 2019** - Mozilla issue report made public and given 'affected' status for Firefox 70.
* **September 23, 2019** - Skype issue report submitted via Microsoft Security Response Center. (VULN-010204)
* **September 25, 2019** - Microsoft classifies issue as reliability issue with Firefox. MSRC case closed.
* **October 18, 2019** - Proof of concept uploaded to GitHub.

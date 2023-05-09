# EndeavourOS Mirror
EndeavourOS uses mainly Archlinux repositories (and so also the Arch Mirrors) system relevant packages, 
in addition we have a small repository holding some packages for setups the installer plus the EndeavourOS Tools.
Aside from the package repository we have one for the ISO itself.

![mirror-structure](https://github.com/endeavouros-team/mirrors/assets/16797647/c9b852af-1c09-42ac-9714-176d3ddab0a6)

 **To add a mirror we need the answers to the following questions to proceed:**
* What bandwidth does your server have? Where is it located?
* What is the url of "our" mirror? (Please make it available under /endeavouros if possible)
* How much disk space are we allowed to occupy? 
* Do you offer public rsync access and if yes, what's the rsync "url"?
* Who is hosting the mirror?
* We plan to have a list of all mirrors and the sponsors in the future, what website should we link for that mirror? And what Sponsor Name?
* Can we use the mirror for both? ISO and repo?
* how often and whether syncing is done.

**General needed specifications and services:**

1. Over 100 Mbits Bandwith.
2. IPV4 and whether IPV6 should be incuded too.
3. Must **not** be behind Cloudflare or similar.
4. Sync with rsync at minimum every 3 hours on a random minute from alpix.eu.rsync.endeavouros.com::endeavouros

**final procedure**
The process of adding your mirror starts with sending an email with the needed informations from above to:
`emailadress@secured`
We will reply to inform you about the next steps so that we can start the internal testing phase.

If our tests are successful, the mirror will be added to the list and distributed to users in our 
[mirror server package](https://github.com/endeavouros-team/PKGBUILDS/tree/master/endeavouros-mirrorlist) 
From that point on your Mirror will be used officially.
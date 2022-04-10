# blocklist
An aggregated blocklist for use in Pi-hole or AdGuard Home

The process to generate this file goes something like this:
* The Firebog "non-crossed" list is pulled down with `curl` from https://v.firebog.net/hosts/lists.php?type=nocross and saved to file.
* The anudeepND Facebook blocklist (https://raw.githubusercontent.com/anudeepND/blacklist/master/facebook.txt) is added to this file.
* This file is then looped over, `curl`ing the contents of each site into a `master_list.txt` file.
* The `master_list.txt` file is then committed and pushed here.

### Justification
I wanted a simple way to keep a "current" blocklist in AdGuard Home, without having to manually check for new lists, etc. This provides me with a process
that I can schedule daily/weekly with a `cron` job, then add this file's URL as a custom blocklist in AdGuard Home. Problem solved.

**Please note**: This was created for my own personal use, however anyone is free to use it. This is a very heavy-handed list and will require a lot of
whitelisting to unbreak things. I recommended starting with something like anudeepND's whitelist - https://github.com/anudeepND/whitelist 


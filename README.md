# Clapi
Simple CLI for Clouding API written in bash. Change variables when needed, use https://api.clouding.io/docs/ as a reference.

Requires jq, jtbl and csvkit (Based Debian).

It is a personal development and independent from Clouding.io, in case of problems with the API contact with their support. 

# Usage Example:

## Help
Run: ```clapi -h```
```sh

⚡ Clapi v1.0.1 for api.clouding.io ⚡

Check API connection... OK  ✓
Check dependencies and KEY... OK  ✓

Usage: clapi [OPTIONS] <INPUT or null>

Options:
 -h         --help              Help menu, provides information on usage.
 -k         --config-key        Change API KEY (accept INPUT).
 -s         --show-key          Show API KEY.
 -ah        --action-history    Show actions history (last 10) or show action with input.
 -sh        --server-history    Show actions server history (last 10).
 -ls        --list-servers      List servers and information related.
 -lssanp    --list-snapshots    List all currently available snapshots.
 -lsbck     --list-backups      List all currently available backups.
 -lsimg     --list-images       List all currently availables images.
 -start     --start-server      Start server (accept INPUT).
 -stop      --stop-server       Stop server (accept INPUT).
 -reboot    --reboot-server     Reboot server (accept INPUT).
 -hard      --hard-reboot       Hard reboot server (accept INPUT).
 -archive   --archive-server    Archive server (accept INPUT).
 -unarchive --unarchive-server  Unarchive server (accept INPUT).
 -resize    --resize-server     Resize server (accept INPUT).
 -vnc       --novnc-url         URL noVNC (accept INPUT).
 -pass      --password          Show password server (accept INPUT).
 -alla      --all-archive       Archive all servers (accept INPUT).
 -allu      --all-unarchive     Unarchive all servers (accept INPUT).
 -cs        --create-server     Create new server (accept INPUT).
 -ds        --delete-server     Delete specified server (accept INPUT).
 -csnap     --create-snapshot   Create new snapshot of specified server (accept INPUT).
 -dssnap    --delete-snapshot   Destroy specified snapshot (accept INPUT).
 -ebs       --enable-backups    Enabled Backups for server (accept INPUT).
 -dbs       --disable-backups   Disable Backups for server (accept INPUT).
 -lsr       --list-fw-rules     List firewall rules for specified group (accept INPUT).
 -lsf       --list-fw-groups    List firewall groups. To create new, use --create-fw-group.
 -cfwg      --create-fw-group   Create new firewall group.
 -cfwr      --create-fw-rule    Create new firewall rule.
 -dfwr      --delete-fw-rule    Delete specified firewall rule (accept INPUT).
 -dfwg      --delete-fw-group   Delete specified firewall group (accept INPUT).
 -er        --enable-rule       Enabled specified firewall rule (accept INPUT).
 -dr        --disable-rule      Disabled specified firewall rule (accept INPUT).

```
## List servers
Run: ```clapi -ls```
```sh
⚡ Clapi v1.0.1 for api.clouding.io ⚡

Check API connection... OK  ✓
Check dependencies and KEY... OK  ✓

| ID               | Name        | Status   | vCore | RAM | Disk | IP             |
| ---------------- | ----------- | -------- | ----- | --- | ---- | -------------- |
| G4bZNnER4qE2Yx7L | linux       | Archived |   1.0 |   2 |   10 | 27.0.232.232   |
| AE1GadQvem8K4kzp | windows     | Archived |   2.0 |   4 |   30 | 217.71.227.152 |
| mOv6yK1JBX1nV0Jj | mikrotik    | Archived |   1.0 |   2 |    5 | 93.189.98.15   |
| BojVWnryDRkK0wav | nginx       | Archived |   2.0 |   4 |   10 | 217.34.231.80  |
| Z7XyD2BorZed4oER | proxmox     | Archived |  10.0 |  20 |  100 | 161.21.34.34   |

Request completed (in 2 seconds).
```
## Installation
Install dependencies:
```sh 
apt install pip jq csvkit -y && pip install jtbl
```  
Install clapi:
```sh 
cd /bin && git clone [URL] && chmod 755 clapi
```  

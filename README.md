# Personal automated recon tools for bug bounty hunting

## Dependencies

- [OWASP Amass](https://github.com/OWASP/Amass)
- [Aquatone](https://github.com/michenriksen/aquatone)
- [S3Scanner](https://github.com/OWASP/Amass)
- [cloud_enum](https://github.com/initstring/cloud_enum)
- [GitHound](https://github.com/tillson/git-hound)

## Directory framework

This is the way I organize my recon loot. I just feed this directory to the tools here.

```
recon
├── target1
│   ├── domains.txt
│   └── subdomains
│       └── 20200101.txt
├── target2
│   ├── domains.txt
│   └── subdomains
│       ├── 20200102.txt
│       └── 20200103.txt
.
.
```

## Enumerate subdomains of targets
- scan through `~/recon` folder for targets using `amass enum -df <subdomains>`
- write results to respective `subdomains/` folders of targets using `amass db -names -df <subdomains> > YYYYMMDD.txt`
- notify for new subdomains using Pushover

Usage:
```
enum

Custom automatic subdomain enumeration tool using amass

Usage: enum path/to/recon [path/to/amass_config.ini]
```

## Scan for vulnerable storages

## Look for leaked credentials in VCS platforms

## Take screenshots and analyze subdomains
- run `aquatone` against collected subdomains and write results to their respective `intel/` folders
- configure aquatone to use `masscan` for scanning ports

## Monitor interesting files and web pages for changes
- scan through `monitor/` folders for files to monitor file changes

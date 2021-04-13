# public-ip-address-lists

WARNING: USE THIS REPO AT YOUR OWN RISK

This repository's goal is to automatically download, parse, and publish commonly-used IP prefix lists into other formats, with as little personal compute or cost as possible.

## Planned Data Sources

| Cloud Provider | Branch | Documentation | IP Network Source | Source is EDL-ready? |
| --- | :-: | :-: | :-: | :-: |
| Amazon Web Services (AWS) | [aws](https://github.com/chrisswinford/public-ip-address-lists/tree/aws) | TBD | [Link](https://ip-ranges.amazonaws.com/ip-ranges.json) | No |
| Google Cloud Platform (GCP) | [gcp](https://github.com/chrisswinford/public-ip-address-lists/tree/gcp) | TBD | [Link](https://www.gstatic.com/ipranges/cloud.json) | No |
| Microsoft Azure (Public Cloud) | [azurecloud](https://github.com/chrisswinford/public-ip-address-lists/tree/azurecloud) | TBD | [Link](https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519) | No |
| Microsoft Azure (China Cloud) | [azurechinacloud](https://github.com/chrisswinford/public-ip-address-lists/tree/azurechinacloud) | TBD | [Link](https://www.microsoft.com/en-us/download/details.aspx?id=57062) | No |
| Microsoft Azure (German Cloud) | [azuregermancloud](https://github.com/chrisswinford/public-ip-address-lists/tree/azuregermancloud) | TBD | [Link](https://www.microsoft.com/en-us/download/details.aspx?id=57064) | No |
| Microsoft Azure (US Government Cloud) | [azureusgovernment](https://github.com/chrisswinford/public-ip-address-lists/tree/azureusgovernment) | TBD | [Link](https://www.microsoft.com/en-us/download/details.aspx?id=57063) | No |

| Threat Provider | Branch | Documentation | IP Network Source | Source is EDL-ready? |
| --- | :-: | :-: | :-: | :-: |
| Abuse.ch SSL Blacklist | TBD | [Link](https://sslbl.abuse.ch/blacklist/) | TBD | TBD |
| DSHIELD Recommended Block List | [dshieldrbl](https://github.com/chrisswinford/public-ip-address-lists/tree/dshieldrbl) | [Link](https://www.dshield.org/xml.html) | [Link](https://www.dshield.org/block.txt) | No |
| FireHOL Block List | TBD | [Link](https://iplists.firehol.org/) | TBD | TBD |
| EmergingThreats Compromised Host List | TBD | [Link](https://doc.emergingthreats.net/bin/view/Main/CompromisedHost) | TBD | TBD |
| MalwareDomainList | TBD | [Link](https://www.malwaredomainlist.com/) | TBD | TBD |
| Spamhaus DROP Lists | [spamhausdrop](https://github.com/chrisswinford/public-ip-address-lists/tree/spamhausdrop) | [Link](https://www.spamhaus.org/drop/) | [Link](https://www.spamhaus.org/drop/drop.txt) | Yes |


# Inspiration
This repo was inspired by https://github.com/jtschichold/panwdbl-actions, which itself was based on ideas from https://github.com/alex/nyt-2020-election-scraper.

# Notes

## Data Sources

### Microsoft Azure

#### Download latest Microsoft Azure lists
https://github.com/MicrosoftDocs/azure-docs/issues/60553

```curl $(curl "https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519" | xmllint --xpath "string(//*[@class=\"mscom-link failoverLink\"]/@href)" -) -o ip.json```

## Output Formats

### PANW EDL Formatting Guidelines
https://docs.paloaltonetworks.com/pan-os/10-0/pan-os-admin/policy/use-an-external-dynamic-list-in-policy/formatting-guidelines-for-an-external-dynamic-list.html

"The external dynamic list can include individual IP addresses, subnet addresses (address/mask), or range of IP addresses. In addition, the block list can include comments and special characters such as * , : , ; , #, or /. The syntax for each line in the list is [IP address, IP/Mask, or IP start range-IP end range] [space] [comment].
Enter each IP address/range/subnet in a new line; URLs or domains are not supported in this list. A subnet or an IP address range, such as 92.168.20.0/24 or 192.168.20.40-192.168.20.50, count as one IP address entry and not as multiple IP addresses. If you add comments, the comment must be on the same line as the IP address/range/subnet. The space at the end of the IP address is the delimiter that separates a comment from the IP address."

## GitHub Actions

### Billing for GitHub Actions
https://docs.github.com/en/github/setting-up-and-managing-billing-and-payments-on-github/about-billing-for-github-actions

### Preinstalled packages on GitHub Actions Runners
https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners




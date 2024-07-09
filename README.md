# Subdomain-Enumeration
all subdomain enumeration

###Subdoamin Enumeration:###
##Juicy Subdomains

subfinder -d target.com-silent dnsx-silent | cut -d-f1| grep --color

*api\dev\/stg\\test\|admin|deno\/stage\/pre\[vpn

## from Buffer Over.run

curls https://dns.bufferover.run/dns?q=.target.com | jqrFDNS_A[] | cut -d', f2 sort -u

## from Riddler.io

curl -s "https://riddler.io/search/exportcsv?q=pld:target.com" | grep -Po "(([\w.-]*)\.([\w]*)\. ([A-Z]))\w+" | sort -u

## from RedHunt Labs Recon API

curl-request GET-url 'https://reconapi.redhuntlabs.com/community/v1/domains/subdomains? domain target.com>&page_size=1000-header X-BLOBR-KEY: APT_KEY' jq.subdomains[]' -r

## from nmap

nmap-script hostmap-crtsh.nse target.com

## from CertSpotter

curl -s "https://api.certspotter.com/v1/issuances?

domain-target.com&include_subdomains=true&expand=dns_names" | jq.[].dns_names | grep -Po"

(([\w.-]*)\.([\w]*)\.([A-z]))\w+" | sort -u

## from Archive

curls "http://web.archive.org/cdx/search/cdx?

url=*.target.com/"&output=text&fl-original&collapse urlkey" | sed -e 's_https://e

"s///// sort -u

## from JLDC

curl -s "https://jldc.me/anubis/subdomains/target.com" | grep -Po "((http|https):\/\/)?

(([\w.-]*)\.([\w]*)\.([A-Z]))\w+" | sort -u

## from crt.sh

curl -s "https://crt.sh/?q=%5.target.com&output=json" | jqr.[].name_value' | sed

's/\\//g' | sortu

## from ThreatMiner

curl -s "https://api.threatminer.org/v2/domain.php?q=target.com&rt=5" | jqr.results[]' |grep

-o "\w.target.com" sort -u

## from Anubis

curls "https://jldc.me/anubis/subdomains/target.com" | jqr| grep -o "\w.target.com"

## from ThreatCrowd

curl -s "https://www.threatcrowd.org/searchApi/v2/domain/report/?domain=target.com" | jq-r

subdomains | grep o "\w.*target.com"

## from Hacker Target

curl -s "https://api.hackertarget.com/hostsearch/?q=target.com"

## from AlienVault

curl -s "https://otx.alienvault.com/api/v1/indicators/domain/tesla.com/url_list?

limit=100&page=1" | grep o "hostname": "[^]*' | sed 's/"hostname": "// | sort -u

## from Censys

censys subdomains target.com

## from subdomain center

curl "https://api.subdomain.center/?domain=target.com" | jqr[] sort -u

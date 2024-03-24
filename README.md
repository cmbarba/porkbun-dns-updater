# porkbun-dns-updater
A bash script for updating A records for domains on porkbun.com. The script uses the JSON processor [jq](https://jqlang.github.io/jq/), the website [ifconfig.me](http://ifconfig.me/), and the [porkbun.com API](https://porkbun.com/api/json/v3/documentation). This script was made because of the desire for a self-hosted dynamic DNS.

## Usage

Edit the example.json file with your own secretapikey, apikey, recordid, and domain from Porkbun. The record ID can be found using the [Retrieve](https://porkbun.com/api/json/v3/documentation#DNS%20Retrieve%20Records%20by%20Domain%20or%20ID) API command.

Run the script with the -f option and json filename. If your current public IP address differs from the current A record, the A record will be updated with your current public IP address.

The script can be run on its own or periodically using a service like cron. At time of writing I am unsure of what kind of rate-limiting Porkbun employs, but once every 5 minutes appears to be safe.
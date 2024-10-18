ReconMyWay - Automated Reconnaissance Tool
ReconMyWay is a Bash script designed to automate web reconnaissance for bug bounty hunting and penetration testing. It combines powerful tools like Subfinder, Assetfinder, httpx-toolkit, Waymore, Katana, and Waybackurls to discover subdomains, identify live endpoints, and gather useful files like JavaScript or backup files. The script includes advanced techniques for WAF bypassing by applying random user agents, IP spoofing, double encoding, and path variation strategies.

Key Features:
Subdomain Enumeration: Combines results from Subfinder and Assetfinder to get a comprehensive list of subdomains.
Live Domain Detection: Uses httpx-toolkit to detect live subdomains, with WAF bypass options.
URL Exploration: Utilizes Waymore, Katana, and Waybackurls to discover and analyze endpoints.
File Extraction: Filters interesting files (e.g., .php, .js, .backup) for further investigation.
WAF Bypass: Adds techniques like random query parameters, double encoding, and path variations to trick basic WAF protections.
Rate Limit Handling: Automatically pauses when encountering rate-limiting (e.g., HTTP 429).
This script makes it easy to automate reconnaissance tasks and prepare for vulnerability discovery, with an emphasis on efficiency and evading WAFs.

Prerequisites:
Ensure you have the following tools installed before running the script:

Subfinder:

bash
Copy code
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
Assetfinder:

bash
Copy code
go get github.com/tomnomnom/assetfinder
httpx-toolkit:

bash
Copy code
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
Waymore:

bash
Copy code
git clone https://github.com/xnl-h4ck3r/waymore.git && cd waymore && pip3 install -r requirements.txt
Katana:

bash
Copy code
go install github.com/projectdiscovery/katana/cmd/katana@latest
Waybackurls:

bash
Copy code
go install github.com/tomnomnom/waybackurls@latest
jq:

bash
Copy code
sudo apt install jq
Ensure these tools are installed and available in your system's PATH.

Usage:
Navigate to the directory where your recon.sh script is located:

bash
Copy code
cd /path/to/your/recon-script
Make the script executable (only needed once):

bash
Copy code
chmod +x recon.sh
Run the script with the target domain:

bash
Copy code
./recon.sh example.com
Next Steps:
You can use the output of this script with tools like Nuclei to run further vulnerability scans on the discovered endpoints.

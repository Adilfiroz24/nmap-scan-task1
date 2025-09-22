# Task 1 — Local Network Port Scanning (Nmap)

## Objective
Discover open ports on devices in the local network to understand network exposure.

## Tools
- Nmap 7.95 (Kali Linux)

## Steps Performed
1. **Host discovery**  
   Command: `nmap -sn 10.63.6.0/24 -oN hosts-scan.txt`  
   Output saved: `hosts-scan.txt`

2. **Quick port scan (common ports)**  
   Command: `sudo nmap -sS -T4 --open -F 10.63.6.0/24 -oN quick-ports.txt`  
   Output saved: `quick-ports.txt`

3. **Full port scan (all ports)**  
   Command: `sudo nmap -sS -p- -T4 --open -oN full-10.63.6.162.txt 10.63.6.162`  
   Output saved: `full-10.63.6.162.txt`

4. **Full scan (no ping)**  
   Command: `sudo nmap -sS -Pn -p- -T4 --open -oN full-10.63.6.162-noping.txt 10.63.6.162`  
   Output saved: `full-10.63.6.162-noping.txt`

5. **Service & version detection**  
   Command: `sudo nmap -sS -sV -p22,80,443 -oN svc-10.63.6.162.txt 10.63.6.162`  
   Output saved: `svc-10.63.6.162.txt`

6. **NSE scripts (default, discovery)**  
   Command: `sudo nmap --script "default,discovery" -p22,80,443 -oN nse-default-10.63.6.162.txt 10.63.6.162`  
   Output saved: `nse-default-10.63.6.162.txt`

## Findings
- Host `10.63.6.107` → Open port `53/tcp (domain)`  
- Host `10.63.6.162` → Open port `1716/tcp (xmsg)`  
- Host `10.63.6.205` → Detected in host discovery (further scans possible)  

## Outcome
- Learned to use Nmap for network reconnaissance.
- Identified devices and open ports in the LAN.
- Understood potential risks of exposed services.

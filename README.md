
# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture

 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:


## SITE

<img width="528" height="573" alt="image" src="https://github.com/user-attachments/assets/ab394c39-d9b2-4c64-a294-048246af7fc4" />

## INURL

<img width="537" height="602" alt="image" src="https://github.com/user-attachments/assets/c8fa5781-39b5-49e7-a1a7-00950e0c2467" />

## INTITLE

<img width="537" height="606" alt="image" src="https://github.com/user-attachments/assets/55a38b74-e816-4e57-b81b-34928a70a873" />

## FILETYPE

<img width="525" height="573" alt="image" src="https://github.com/user-attachments/assets/4661a0c5-572a-4b10-a172-243aeae89595" />

## INTEXT

<img width="537" height="602" alt="image" src="https://github.com/user-attachments/assets/eb464464-a5d9-47af-ae2b-7c542f7371e1" />

## LINK

<img width="533" height="601" alt="image" src="https://github.com/user-attachments/assets/87a3f911-c77b-43fe-a9bb-10e0d5f994e2" />

## CACHE

<img width="536" height="601" alt="image" src="https://github.com/user-attachments/assets/7497cf3a-7456-43bf-8c67-1a79a2d81d2d" />

## EXT

<img width="542" height="606" alt="image" src="https://github.com/user-attachments/assets/780ca341-e4e6-4995-8b19-e3162917a74b" />

# DNS Enumeration

<img width="660" height="532" alt="image" src="https://github.com/user-attachments/assets/489c4c06-8127-453d-85b6-0d9bda8c39bb" />



## DNS Recon

<img width="557" height="496" alt="image" src="https://github.com/user-attachments/assets/91fe4ec1-a089-4539-9ae7-df3809eff974" />


| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:

## NSLOOKUP

<img width="492" height="781" alt="image" src="https://github.com/user-attachments/assets/49f124e3-3ee1-48cd-820e-e1b469fdccdd" />

## DIG

<img width="613" height="611" alt="image" src="https://github.com/user-attachments/assets/6797be99-ea6d-4597-ae96-30f740ac645b" />

## HOST

<img width="635" height="397" alt="image" src="https://github.com/user-attachments/assets/293a13da-e834-46d7-886c-241a2daff0ad" />

## DNSSENUM

<img width="682" height="528" alt="image" src="https://github.com/user-attachments/assets/2abb3da7-bccc-432f-9be4-ec259f4cd6ca" />

## DNSRECON

<img width="602" height="517" alt="image" src="https://github.com/user-attachments/assets/114c22d5-cf56-4367-ab87-ebd4099a34df" />

## FIERCE

<img width="602" height="697" alt="image" src="https://github.com/user-attachments/assets/71a6b984-196c-4822-bf4e-a64d66547d75" />


## HARVESTER

<img width="600" height="637" alt="image" src="https://github.com/user-attachments/assets/610e611e-01ee-478f-92f3-43cfc0e98939" />



## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```

## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:

<img width="670" height="450" alt="image" src="https://github.com/user-attachments/assets/55330fd9-008e-4865-9fd0-147d709cad02" />



## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
  
<img width="1250" height="713" alt="image" src="https://github.com/user-attachments/assets/a4380dff-b526-47f6-b236-5e6517cc587b" />



## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:

<img width="1275" height="263" alt="image" src="https://github.com/user-attachments/assets/63e6ad96-1535-46af-85ea-97afc5245020" />




## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully

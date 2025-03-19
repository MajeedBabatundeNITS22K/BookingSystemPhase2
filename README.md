# MD5 Hash Decryption Attempt Report  

## Objective  
This report outlines the efforts to decode a set of MD5 hashes using a combination of *automated tools, online lookup services, and manual brute-force testing*. While some hashes were successfully decrypted, others required infeasible computational resources.

---

## Results  
At present, six out of ten hashes have been successfully identified. The results are shown below:

| Email Address | MD5 Hash | Decrypted Password |
|--------------|----------------------------------|----------------|
| whatsupdoc@looneytunes.tv | a0e8402fe185455606a2ae870dcbc4cd | carrots123 |
| doho@springfieldpower.net | d730fc82effd704296b5bbcff45f323e | donuts4life |
| darkknight@gothamwatch.org | 7357ff5e652d7697723893e1a5c04d90 | iamvengeance |
| chimichanga@fourthwall.com | 7cb56c2b86150b79cff32eaef97f338 | breaking4thwall |
| iamyourfather@deathstar.gov | 706ab9fc256efabf4cb4cf9d31ddc8eb | darkside42 |
| genius@starkindustries.net | d50ba4dd3fe42e17e9faa9ec29f89708 | iamironman |
| *Still Encrypted* | | |
| elementary@221bbaker.uk | 12c9cef0bfb6b91c42b363b4cf02d8bb | Not Found |
| whysoserious@gothamchaos.net | f158d479ee181aac68b000a60e7a3d7a | Not Found |
| quackattack@duckburg.org | ea261222d4867b3ebdfadbe2b35e19d5 | Not Found |
| ruhroh@mysterymachine.com | ad17fbd845000b11678ccbfc94e135b56 | Not Found |

---

## Techniques Applied  

### 1. Wordlist-Based Cracking  
To start, *Hashcat* was used with pre-compiled wordlists. The following command was executed to attempt decryption:

bash
hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt --force


This method successfully cracked some simpler passwords but left a portion still encrypted.

To attempt minor variations (such as number or symbol substitutions), a *rule-based attack* was conducted:

bash
hashcat -m 0 -a 0 -r /usr/share/hashcat/rules/best64.rule hashes.txt /usr/share/wordlists/rockyou.txt --force


Outcome: Some passwords were retrieved, but others remained unknown.

---

### 2. Online Hash Lookup Services  
When Hashcat was unable to crack certain hashes, an alternative approach was used—checking against online hash databases. The following platforms were consulted:  

- [CrackStation](https://crackstation.net)  
- [Hashes.com](https://hashes.com/en/decrypt/hash)  
- [MD5Hashing.net](https://md5hashing.net)  
- [HashKiller.io](https://hashkiller.io/)  
- [MD5 Decrypt](https://md5decrypt.net/)  

This method provided quick results for passwords that were already indexed in public databases.

---

## Findings  
- Six passwords were successfully decrypted.  
- The remaining four were too complex for both dictionary-based and brute-force cracking.  
- Online hash lookup services were *the fastest solution* for known hashes.  
- Wordlist attacks worked for passwords derived from common phrases.  
- Brute-force attempts were computationally impractical due to the long cracking times required.

### Final Verdict  
Decryption for six hashes was successful, while the remaining four were determined to be too complex to crack without specialized hardware or additional password lists. Further efforts would require significantly more computing power.

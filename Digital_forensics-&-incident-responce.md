# Digital Forensics and Incident Responce

<h3>DFIR</h3> It is a specialized field that investigates cyber incidents by collecting, analyzing, and preserving digital evidence to understand the nature of an attack, identify perpetrators, and prevent future incidents


<h3>Digital forensics </h3> Is the identifying forensic artifacts or evidence  of human activity in digital devices.


<h3>Incident response</h3> It is the process of using cyber security expertize and leveraging forensic information to identify activities of interest from security perspective.


<h3>Cyber crimes</h3> These are crimes conducted via the internet or any computer network.


****


## Types of digital forensics.

- Computer forensics 
- Database forensics 
- Mobile device forensics
- Network forensics  


## Required Skills

### Technical skills 
- Programming languages
- Common operating systems
- Hardware & Software proficiency
- Technical writing
- Project management
- Data analysis
- Cyber security standards 

### Soft skills 
- Analytical & curious mind.
- Confidentiality 
- Perseverance 
- Good communication skills 



## Applications of Forensics

- Legal investigations
- Corporate security incidents
- Cybersecurity research. 



## LAWs

- Federal Information Security Management Act(FISM)
- Gramm-Leach Bliley Act(GLBA)
- Health Insuarance Portability & Accountability Act(HIPAA)
- PCI- Data Security Standards 




## Forensics career

### 1. Law enforcement agencies 
- Federal bureau investigation (FBI)
- Interpol

### 2. Cyber security firms
### 3. Private firms



-------------------------------------------------------------






# Phases of Forensics.

### NIST standard process

1. Preparation 
2. Detection and Analysis 
3. Containment, Eradication, Recovery 
4. Post-incident Activity


### SANS standard process (PICERL)

1. P - Preparation 
2. I - Identification 
3. C - Containment 
4. E - Eradication 
5. R - Recovery 
6. L - Lessons learned


### My Symplified interpretation
​
1. Identification(What evidence is needed) 
- Understanding hacker footprints

2. Preservation(Integrity)

3. Analysis(Data insights)
- Network traffic analysis
- Using OSINT tools for investigation
- Log monitoring for threat detection

4. Documentation & Report
- Write down a comprehensive report on the findings.

5. Presentation(Deliver evidence)
- Present your documentation to the relevant authorities. 


 


-------------------------------------------------------------




# Identification Phase

- Understanding hackers' footprints and collecting required evidence from scene.



## Interview/ interrogation 

- The ability to ask questions in a way that maximizes the amount of true information the investigator knows 


❌Most people are likely to lie ie exaggerate information.

📌Close sources are high quality & trustworthy



## Data Recovery

An attempt to pull out as much information from the data as possible.

- Collect broken hard drives
- Crashed servers
- Recover deleted files
- Look into compromised devices 

### Tools

- Photorec
- tsk_recover
- The sleuth kit
- foremost 
- Extudelete
- USBRip - history of USB events



 
## Event reconstruction 

Traditional forensics analysis 
- Fingerprints
- Blood
- Hair
- Handwriting
- Currency 

### Tools

- Velociraptor [Velociraptor Documentation](https://docs.velociraptor.com)

## Undercover investigation 

Is where a digital forensics guy pretends to be an attacker to gain community trust so as to get more first hand information.

### Camouflage/hide/be part of hackers:

- Darkweb marketplaces
- Hacker forums
- Hackers social groups i.e Reddit, WhatsApp, facebook etc






-------------------------------------------------------------





# Preservation phase.

This process ensures that our digital evidence is not contaminated and remains safe while analyzing.


### Chain of custody 
Any person not related to the investigations must not posses the evidence.

### Order of volatility 
Digital forensics is often volatile(will be lost forever if not captured in time)
i.e RAM

### Timeline creation 
A timeline of events needs to br created for efficient and accurate analysis.

Tools 
Kroll Artifact Parser & Extractor(KAPE)






-------------------------------------------------------------





# Intelligence gathering 

### Open source intelligence 

- Publicly available 
- Github
- Social media content 


### Close source intelligence 
This is information gained from non-public sources.

- Past cases
- Law enforcement 
- Police operations 
- Millitary & intelligence sources 
- Private organizations
- Internet service providers (ISP)





-------------------------------------------------------------





# Disk Analysis




### Tools

- Autopsy - [Sleuthkit](https://sleuthkit.org/autopsy/)
- Bulk_extractor
- Fiwalk



### Password cracking

- This techniques will enable you to unlock compromised media. 

### Password cracking Tools
- John the ripper
- Hashcat
- Aircrack-ng 
- Cain and Abel
- DVCS Ripper






-------------------------------------------------------------






# Memory Analysis

Most valuable information can be found within memory dumps(RAM image files)


### Memory Analysis Tools

- Volatility: [Volatility Foundation](https://volatilityfoundation.org)
- Python - imageinfo, pslist, psscan etc.


### Volatility workflow

1. Run strings for clues.
2. Identify the image profile i.e OS type, version etc.
3. Dump processes & look for suspicious processes.
4. Dump data related to interesting processes.
5. View data in a format relating to the process i.e word: .docx, notepad: .txt etc

- Profile identification 
 
      $python vol.py -f ~/images.raw imageinfo

- Dump processes 

      $python vol.py -f ~/image.raw pslist --profile=Win7SP0x64 pstree

- Process memory dump

      $python vol.py -f ~/image.raw --profile=Win7SP0x64 memdump -p 2019 -D dump/





-------------------------------------------------------------







# Network Analysis

### Tools
- Snort
- nmap
- tcpdump






-------------------------------------------------------------





# Documentation and Reporting    


The report Should be:

✅Clear

✅ Concise 

✅ Consistent 

### Documentation Tools

- Word processor 





-------------------------------------------------------------




# Useful resources

### Websites

- https://forensics.wiki/

### Videos & tutorials

- 13cubed youtube channel





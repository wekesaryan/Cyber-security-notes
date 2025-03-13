 # Ethics 🔹 Laws 🔹 Legal 🔹 Standards

# Common standards.
1. NIST
2. ISO
3. CSF
4. CIS
5. RMF
6. CISA

📌 Don't learn to hack, hack to learn.

  #Ethical Hacking Bodies.

1. Computer fraud and abuse Act (CFAA)
2. INTERPOL
3. International Telecommunication Union(ITU)
4. Kenya Computer Incident Response Team Coordination Center (National KE-CIRT/CC)
5. NSO
6. The Children Online Privacy Protection Act 

--------------------------------------------------------------

##       Hacking Motives/goals 
1. Challenge - learn
2. Recognition - bond, acquire
3. Curiosity - learn
4. Ideology - political, religious 
5. Greed - money
6. State-sponsored
7. Cooperate espionage - spying


Attack = Motive + method + vulnerability

📌Hackers are not criminals, they are explorers and inventors.
📌Never trust anybody.



 Elements of information security 
          C.I.A triad

C - Confidentiality
ℹ️ - Integrity
🅰️ - Availability

📌There exists no perfectly secure system.
📌 Secrecy is security.



--------------------------------------------------------------

    Hacker skill levels
        
          Script kiddies(begginer)
                  ↓

          Green hat(basic techniques)
                  ↓
            Hacker group 
          Whistle blowers
                  ↓
          Hactivist(advanced techniques)
                  ↓   

          Botnet hackers
                  ↓   

          Cyber terrorist 

Hacker skill sets.

       Technical skills 
- Operating system knowledge 
- Computer Networking skills 
- Hardware & software capabilities
- Past vulnerabilities & attacks
- Software development 

     Non-technical skills 
- Learning ability 
- Problem solving skills 
- Communication skills 
- Laws & regulations awareness 


-----------------------------------------------------------------

     Types of hackers.

1. White hat - ethical 
2. Grey hat - neutral 
3. Black hat - bad guy

Red team - attackers 
Blue team - defenders 
Yellow team - builders

 


-----------------------------------------------------------------

 #   Phases of hacking 
  
1. Information gathering
2. Scannning and Enumeration
3. Exploitation/Gaining access
4. Post exploitation / Maintaining Access
5. Clearing tracks
6. Analysis and reporting 

-----------------------------------------------------------------


# Hacking Lab set-up.

Virtual environment. 
- VMware workstation player
- Oracle Virtual Box
- Windows sandbox 
-  


##        Hacking OS
- Kali linux
- Parrot
- Backbox
- Pentoo
- DracOS
- Cyborg
- Deft linux
- Backarch
- Arch strike
- Mobelexr - Mobile apps
- Pentest Box   
- Windows Subsystem for Linux (WSL)
- Rooted Mobile phone 

Vulnerable tools.

- Metasploitable 1 & 2
- Windows 2000, 2003, 07, 08, 10, 11
- Quoar
- Sedna
- Badstore 
- OWASP Broken Web Application VM
- Hack This Site
- Root me
- Hacker 101
- Capture The Flag 101
- Hack-A-Sat
- Try hack me
- Hack The Box 


    Essential tools
Reconnaissance phase
- Nmap
- Maltego-ng 
- Recon-ng
- Shodan
- theHarvester

Scanning and enumeration 
- Wireshark
- Nessus 
- Nikto
- OpenVAS
- Burp Suite

Exploitations 
- Metasploit framework 
- SQLmap
- John the Ripper 
- Hydra
- Aircrack-ng 

Maintaining Access 
- Cobalt strike 
- Empire
- Mimikatz
- Netcat
- PowerSploit


          
#      Kali Linux.


$sudo apt update &- sudo apt upgrade -y
$ sudo -i enable root , -l disable root
$ sudo apt-get autoremove
$sudo apt-get autoclean


---
   Optimize/customize Kali linux.

1. Use a Lightweight Desktop Environment i.e LXQt, Openbox, or i3.
Install LXQt (Lightweight alternative to XFCE)

$sudo apt install kali-desktop-lxqt -y
$sudo apt install openbox obconf obmenu -y
$sudo apt remove --purge kali-desktop-xfce -y
$sudo apt autoremove -y

---
2. Remove Unnecessary Tools & Packages
$dpkg --get-selections | grep kali
$sudo apt remove --purge kali-linux-forensic kali-linux-voip kali-linux-wireless -y
$sudo apt autoremove -y

To remove all Kali hacking tools and keep only the essentials:
$sudo apt remove --purge kali-linux-default -y
$sudo apt autoremove -y

If you only need specific tools, install them manually instead.

---

3. Reduce Background Services & Daemons

Check Running Services
$systemctl list-unit-files --type=service | grep enabled

Disable Unnecessary Services
$sudo systemctl disable $bluetooth.service
$sudo systemctl stop bluetooth.service

Disable NetworkManager-wait-online, which can slow down boot times:
$sudo systemctl disable NetworkManager-wait-online.service

---

4. Optimize Storage & Clean Up Junk Files

Remove Old Dependencies & Cached Packages

$sudo apt autoremove -y
$sudo apt autoclean -y
$sudo apt clean -y

Delete Log Files
$sudo rm -rf /var/log/*

Check for Large Unused Files & clear it:
$du -sh /var/cache/apt
$sudo rm -rf /var/cache/apt/archives/*

---

5. Reduce RAM Usage & Improve Performance

Use ZRAM (Compressed Swap in RAM)
$sudo apt install zram-tools -y
$sudo systemctl enable --now zramswap.service

Reduce Swappiness
$echo 'vm.swappiness=10' | sudo tee -a /etc/sysctl.conf
sudo sysctl -p

---

6. Optimize Boot Speed

Disable Unnecessary Boot Services
$systemctl list-unit-files --type=service --state=enabled

Disable unneeded services:
$sudo systemctl disable <service-name>

Use Systemd-analyze to Check Boot Time
$systemd-analyze
$systemd-analyze blame

---

7. Optimize Network & DNS for Faster Browsing

Use a Fast DNS Resolver
Edit /etc/resolv.conf:
$sudo nano /etc/resolv.conf

Replace with:
nameserver 1.1.1.1
nameserver 8.8.8.8

Then, prevent automatic changes:
&sudo chattr +i /etc/resolv.conf


---

8. Install a Lighter Terminal Emulator

Instead of using GNOME Terminal, switch to Alacritty or Kitty:

$sudo apt install alacritty -y


---

9. Use a Minimal Kernel (Optional)

You can install a minimal kernel for lower RAM usage:
$sudo apt install linux-image-rt-amd64 -y

---

10. Reboot your system to apply all optimizations:
$sudo reboot


---

✅ Reduced Storage Usage by removing unnecessary packages
✅ Faster Boot Time by disabling unneeded services
✅ Lower RAM Usage with ZRAM and swappiness tuning
✅ Improved Network Speed with optimized DNS

-----------------------------------------------------------------

#  Custom Kali Linux ISO.

1. Install live-build and Dependencies

$sudo apt update && sudo apt install -y live-build cdebootstrap curl git

---

2. Clone the Kali Linux ISO Builder

$git clone https://gitlab.com/kalilinux/build-scripts/live-build-config.git
$cd live-build-config

---

3. Remove Unnecessary Packages

$nano kali-config/variant-default/package-lists/kali.list.chroot

Remove unnecessary tools:
Delete lines for forensics, VoIP, and wireless tools if you don’t need them.

Add performance tools:
Add ZRAM, a lightweight terminal, and network optimizations:

zram-tools
alacritty
resolvconf

Save and exit (CTRL + X, then Y, then ENTER).

---

4. Optimize System Settings

$nano kali-config/common/includes.chroot/etc/sysctl.conf

Add:

vm.swappiness=10
fs.inotify.max_user_watches=524288
net.core.default_qdisc=fq
net.ipv4.tcp_congestion_control=bbr

Save and exit.


---

5. Customize Boot Services

Disable unnecessary services by creating a script:

$nano kali-config/common/hooks/00-disable-services.chroot

Add:

#!/bin/bash
systemctl disable bluetooth.service
systemctl disable NetworkManager-wait-online.service
systemctl disable ModemManager.service

Save, then make it executable:

chmod +x kali-config/common/hooks/00-disable-services.chroot


---

6. Build the Custom ISO

Run the following command to start the ISO build process:

$sudo ./build.sh --variant default --verbose

This will take some time depending on your system’s performance.


---

7. Test Your Custom Kali ISO

Once the build is done, find your ISO in the images/ folder:

$ls -lh images/

Now, test it in VMware or VirtualBox:

Create a new VM and select your custom ISO as the installation medium.

---

✅ Optimized performance (faster boot, reduced RAM usage)
✅ Reduced storage (removed unneeded tools)
✅ Customized networking & security settings.
❌ Kernel & system updates might introduce new settings that need re-tweaking.
❌ DNS and network settings might be reset unless locked.


-----------------------------------------------------------------

# Parrot Security OS.

$sudo su
$passwd root
$ apt update && apt upgrade -y

Install your preffered media player
i.e media codecs

Install graphics drivers
i.e nividia

Install parrot metapackages
$sudo apt install parrot-tools-full

Install your penetration tools
- Angry IP scanner
- Nessus




-----------------------------------------------------------------

#        Metasploit Framework 

   Components of MF
1.Exploit
2.Payload
3.Modules
4.Listeners 
5.Shellcodes



  Utilities
1. Msfpayload - generate shellcodes, executables
2. MSFencode - evade antivirus 
3. Nasm shell - identify opcodes(assembly instructions)


    Interfaces
1. MsfConsole
2. Armitage - GUI

http://www.fastandeasyhacking.com

$sudo apt install armitage
$sudo armitage
$service postresql start
$service metasploit start



3. Metasploit express - web interface

4. Meterpreter - remote shell



-----------------------------------

#       Metasploitable 3.

     System requirements 
1. 65 GB available disk space
2. 4.5 GB RAM
3. Vagrant
4. Vagrant reload plugin
5. Packer
6. Git clone metasploitable 3

Installation 

       1. Vmware

>Vagrant plugin install vagrant-vmware-desktop
>vagrant plugin install vagrant-reload
>vagrant box list
>vagrant box add rapid7/metasploitable3-win2k8 --provider vmware_desktop
>vagrant box remove rapid7/metasploitable3-ub1404 --provider vmware_desktop
>vagrant up OR >vagrant up win2k8

In vagrant dir
 >slmgr /rearm
>. \build.ps1
>. \build.ps1 windows2008 or Ubuntu 1404


           2. Virtual box

>vagrant plugin install vagrant-vbguest
>vagrant plugin install vagrant-reload
>set-ExecutionPolicy Unrestricted
>.\build.ps1
>.\build.ps1 windows2008 or Ubuntu 1404

    OR

>. \packer.exe build. \windows_10_choco.json
>Vagrant box add win10 windows_10_virtualbox.box
>cd win10
>vagrant init win10
>vagrant up


Username: Vagrant passwd : vagrant



Rooting Android phone

Requirements/Tools
1. Island apk
2. Magisk
3. Termux
4. Kali Linux
5. Cometin
6. OEM enabled on Android developer options.
7. Fdroid
8. VNC

     Enabling OEM before rooting 
$adb reboot recovery
$adb devices
$adb sideload update.zip

$termux-setup-storage
$wget -O install-nethunter-termux https://offsec/zMcrZWr
$chmod +x install-nethunter-termux
$./install-nethunter-termux 
$nethunter -r -> root access 
$kex passwd -> set VNC password 
$kex & -> launch VNC server


-----------------------------------------------------------------


# Potential Targets.

1. Financial institutions 
        - Bank
        - Cryptocurrency
        - Saccos
        - Mobile banking
        - ATM machines
        - Supply chain vendors    

2. Infrastructure 
      - electric grids
      - natural gas lines
      - Electric vehicles

3. Systems
      - E-commerce 
      - Betting - money
      - School - fee records, report cards
      - Healthcare - patients records 
      - Voting systems
      - Tax authority ie KRA


4. Social media
      - Meta(FB, IG, WhatsApp)
      - X
     - LinkedIn
     - Telegram,Signal, 

5. AI models
      - Jailbreak chatbots
      - IoT devices

6. Computer Networks 
      - Wi-fi, Server, router
      - Surveillance - CCTV, Webcams
      - Satellites communication

7. Video games
       - make game easier
       - Coins, wins, strength 

8. Bussiness 
     - Valuable data - credit cards, ID
     - Espionage - spying competitors

9. Telecommunication 
         - Calls & SMS 
         - TV & Radio channels 

-----------------------------------------------------------------


#     Some useful chrome extensions

1. Cookie editor
2. Firebug lite for google chrome
3. D3coder
4. EndPointer
5. Built with 
6. Form fuzzer
7. Session manager
8. Request maker
9. Shodan
10. XSS rays
11. WebSecurify
12. Port scanner
13. XSS chef
14. HPP finder
15. The exploit database
16. GHDB
17. IP address and domain information
18. Retire js
19. Temper monkey 
20. Foxy proxy
21. Site spider










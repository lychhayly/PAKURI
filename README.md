# PAKURI: Penetration Test Achieve Knowledge Unite Rapid Interface

![logo](img/pakuri-banner.png)  
![version](https://img.shields.io/github/v/tag/01rabbit/PAKURI?label=Version)
![License](https://img.shields.io/github/license/01rabbit/PAKURI)
![release-date](https://img.shields.io/github/release-date/01rabbit/PAKURI)
![sns](https://img.shields.io/twitter/follow/PAKURI9?label=PAKURI&style=social)

---

[Japanese](README_ja.md)

## Overview

PAKURI is a penetration test tool with a terminal user interface (TUI) that can be operated with just the keypad.

![overview](https://user-images.githubusercontent.com/16553787/80278942-4fcbe380-8735-11ea-825d-61f662c4754a.png)

### Presentation

* November 2nd,2019: [AV TOKYO 2019 Hive](http://ja.avtokyo.org/avtokyo2019/event)
* December 21-22th,2019: [SECCON YOROZU 2019](https://www.seccon.jp/2019/akihabara/)

### What's PAKURI

I've consulted many pen testing tools. I then took the good points of those tools and incorporated them into my own tools. In Japanese slang, imitation is also called "paku-ru".
> ぱくる (godan conjugation, hiragana and katakana パクる, rōmaji pakuru)
>
> 1. eat with a wide open mouth
> 2. steal when one isn't looking, snatch, swipe  
> 3. copy someone's idea or design  
> 4. nab, be caught by the police  
>
> [Wiktionary:ぱくる](https://en.wiktionary.org/wiki/%E3%81%B1%E3%81%8F%E3%82%8B "ぱくる")

---

## Description

PAKURI is a semi-automated, user-friendly framework for penetration testing tools. Using only the keypad, you can use the penetration test tool like a game.  
It's also a great introductory tool for beginners. Learn the flow of penetration testing with PAKURI without having to wrestle with confusing command lines and tools.

---

## Your benefits

By using our PAKURI, you will benefit from the following.  

For redteam:  
  (a) Red Teams can easily perform operations such as information enumeration and vulnerability scanning.  
  (b) Visualizing the survey results is possible only with the numeric keypad.

For blueteam:  
  (c) The Blue Team can experience a dummy attack by simply operating the numeric keypad even they do not have any penetration testing skill.  

For beginner:  
  (d) PAKURI has been created to support the early stages of penetration testing. These can be achieved with what is included in Kali-Tools. It can be useful for training the entry level pentesters.

|**NOTE**  |
|:----------------|
|If you are interested, please use them in an environment **under your control and at your own risk**. And, if you execute the PAKURI on systems that are not under your control, it may be considered an attack and you may have legally liabillity for your action.|

---

## Features

### Intelligence gathering

* Port Scan
  * [Nmap](https://tools.kali.org/information-gathering/nmap)
  * [nmap_vulners](https://github.com/vulnersCom/nmap-vulners)
* Enumeration
  * [enum4linux](https://tools.kali.org/information-gathering/enum4linux)
  * [Nikto](https://tools.kali.org/information-gathering/nikto)
  * [sslscan](https://github.com/rbsec/sslscan)
  * [SSLyze](https://tools.kali.org/information-gathering/sslyze)

### Vulnerability analysis

* Vulnerability Scan
  * [OpenVAS](https://tools.kali.org/vulnerability-analysis/openvas)
* Web Application Scan
  * [Skipfish](https://tools.kali.org/web-applications/skipfish)

### Exploit

* Brute Force Attack
  * [BruteSpray](https://tools.kali.org/password-attacks/brutespray)
* Exploitation
  * [Metasploit](https://tools.kali.org/exploitation-tools/metasploit-framework)
  * Exsploit Database - [searchsploit](https://tools.kali.org/exploitation-tools/exploitdb)

### Misc

* Visualize
  * [Faraday](https://github.com/infobyte/faraday.git)
* CUI-GUI switching  
  PAKURI can be operated with CUI and does not require a high-spec machine, so it can be operated with Raspberry Pi.

---

## Install

1. Update your apt and install git:  

    ```shell
    kali@kali:~$ sudo apt update
    kali@kali:~$ sudo apt install git
    ```

2. Download the PAKURI installer from the PAKURI Github repository:

    ```shell
    kali@kali:~$ git clone https://github.com/01rabbit/PAKURI.git
    ```

3. CD into the PAKURI folder and run the install script:

    ```shell
    kali@kali:~$ cd PAKURI  
    kali@kali:~/PAKURI$ chmod +x install.sh
    kali@kali:~/PAKURI$ sudo ./install.sh
    ```

4. Register the OpenVAS administrator user and password in pakuri.conf:

    ```shell
    kali@kali:~/PAKURI$ vim pakuri.conf
    ...snip...

    # OpenVAS
    OMPUSER="admin"
    OMPPASS="admin"
    ```

5. Faraday-server is started. After starting up, access from your browser and register your workspace:

    ```shell
    kali@kali:~/PAKURI$ sudo systemctl start faraday-server.service  
    kali@kali:~/PAKURI$ firefox localhost:5985
    ```

6. Register the workspace you just registered in pakuri.conf:

    ```shell
    kali@kali:~/PAKURI$ vim pakuri.conf
    ...snip...

    # Faraday
    WORKSPACE="test_workspace"
    ```

---

## Usage

```shell
kali@kali:~/PAKURI$ ./pakuri.sh
```
![startup](https://user-images.githubusercontent.com/16553787/80306953-31e19b80-8794-11ea-8a50-554dafe65294.gif)  
PAKURI is not fully automated and requires the user interactions, to make sure to proceed the pentest and to avoid any unintended attack or trouble.  

---

## Keypad Operation

![keypad](https://user-images.githubusercontent.com/16553787/80306868-da433000-8793-11ea-9b5b-4e2b82ba3254.gif)  
By operating the numeric keypad, it is possible to scan the network, scan for vulnerabilities, and perform simple pseudo attacks.

---
## Demo

[![](https://img.youtube.com/vi/wr9i2NsaqPc/0.jpg)](https://www.youtube.com/watch?v=wr9i2NsaqPc)

---

## Operation check environment

* OS: KAli Linux 2020.1
* Memory: 8.0GB

## Known Issues

This is intended for use Kali Linux. Operation on other OS is not guaranteed.

---

## Contributors

If you have some new idea about this project, issue, feedback or found some valuable tool feel free to open an issue for just DM me via [@Mr.Rabbit](https://twitter.com/01ra66it) or [@PAKURI](https://twitter.com/PAKURI9).

### Special thanks

Thanks to [@cyberdefense_jp](https://twitter.com/cyberdefense_jp) for contribute so many awesome ideas to this tool.

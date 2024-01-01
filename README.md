# HAL13ERD

<p align="center">
<img align="left" src="./img/HAL13ERD_logo.png" width="300" alt="project logo">
</p>

<br>

## Description

HAL13ERD is a Kali virtual machine created with the intent to gather various OSINT tools to perform basic OSINT investigations. This project's objective is to replicate the once-known Buscador Virtual Machine by creating your version.

<br>
<br>
<br>
<br>
<br>

> [!NOTE]
> This project was created for educational purposes. OSINT tasks were executed on dummy accounts.

## OSINT Tools

The following tools used in the project are listed below:
* [Sherlock](#Sherlock)
* [TheHarvester](#theHarvester)
* [GHunt](#GHunt)
* [Social_Mapper](#social_mapper)
* [EXIF Tool](#EXIF-Tool)
* [PhoneInfoga](#PhoneInfoga)
* [Osintgram](#Osintgram)

## Sherlock
Sherlock, a powerful command line tool used to find usernames across many social networks.

### ⚙️ Setup
Write the following code to install the tool on Kali:

Clone the repository:
```
git clone https://github.com/sherlock-project/sherlock.git
```

Navigate to the directory:
```
cd sherlock
```

Install the requirements:
```
python3 -m pip install -r requirements.txt
```

Use `python3 sherlock --help` to list all possible commands that can be used.

For further help, you may refer to the [Sherlock](https://github.com/sherlock-project/sherlock) repository.

## theHarvester
theHarvester performs open source intelligence (OSINT) gathering to help determine
a domain's external threat landscape. The tool gathers names, emails, IPs, subdomains, and URLs by using multiple public resources.


### ⚙️ Setup
Write the following code to install the tool on Kali:
```
sudo apt install theharvester
```
Use `theHarvester -h` to list all possible commands that can be used.

For further help, you may refer to [theHarvester](https://www.kali.org/tools/theharvester/).

## GHunt
GHunt is an offensive Google framework, currently focused on OSINT. It is used to extract Gmail ID details.


### ⚙️ Setup
:
Clone the GHunt repository and navigate to the directory:
```
git clone https://github.com/mxrch/GHunt.git    
cd GHunt
```
Install the requirements for GHunt:
```
sudo pip3 install -r requirements.txt
```

Install **pipx** to install ghunt:
```
cd $HOME
pip3 install pipx
pipx ensurepath
pipx install ghunt
```

First, launch the listener by doing `ghunt login` and choose between 1 of the 2 first methods :

> [!TIP]
> **Option 1** is recommended as it is easier method for gmail login.

```
$ ghunt login

[1] (Companion) Put GHunt on listening mode
[2] (Companion) Paste base64-encoded cookies
[3] Enter manually all cookies

Choice =>
```

Then, use GHunt Companion to complete the login.

The extension is available in the following stores :\
\
[![Firefox](https://files.catbox.moe/5g2ld5.png)](https://addons.mozilla.org/en-US/firefox/addon/ghunt-companion/)&nbsp;&nbsp;&nbsp;[![Chrome](https://storage.googleapis.com/web-dev-uploads/image/WlD8wC6g8khYWPJUsQceQkhXSlv1/UV4C4ybeBTsZt43U4xis.png)](https://chrome.google.com/webstore/detail/ghunt-companion/dpdcofblfbmmnikcbmmiakkclocadjab)

<br>

> [!NOTE]
> After login, your Gmail credentials are stored in **ghunt/creds.m**.

<br>

Use `ghunt -h` to list all possible commands that can be used.

To get details on target email:
```
ghunt email <email_address>
```
You can also use --json with email, gaia and drive modules to export in JSON
```
ghunt email <email_address> --json user_data.json
```


For further help, you may refer to the [GHunt](https://github.com/mxrch/GHunt) repository.


## social_mapper
Social Mapper is an Open Source Intelligence Tool that uses facial recognition to correlate social media profiles across different sites on a large scale. 

### ⚙️ Setup

Get the non-ESR version of Firefox with:
```
sudo add-apt-repository ppa:mozillateam/firefox-next && sudo apt update && sudo apt upgrade
```

Download the latest version of Geckodriver here:
```
https://github.com/mozilla/geckodriver/releases
```
Install Geckodriver and copy the file to **/usr/bin/**:
```
cd Downloads/
tar -xvzf <geckodriver tar installer name>.gz
sudo cp geckodriver /usr/bin/
```
Install the following prerequisites:
```
sudo apt-get install build-essential cmake
sudo apt-get install libgtk-3-dev
sudo apt-get install libboost-all-dev
```
Finish installation with:
```
git clone https://github.com/Greenwolf/social_mapper
cd social_mapper/setup
python3 -m pip install --no-cache-dir -r requirements.txt
```
Now `cd ..` and run:
```
python social_mapper.py -h
```
Paste your target image in the imagefolder(**social_mapper/Input-Examples/imagefolder/**) before executing any social_mapper OSINt peration



For further help, you may refer to the [social_mapper](https://github.com/Greenwolf/social_mapper) repository.



## EXIF Tool
EXIF Tool is a platform-independent command-line application for reading, writing, and editing meta information in a wide variety of files. This script version is created by David Bombal.

### ⚙️ Setup
Write the following code to install the tool on Kali:

Create a new EXIF Tool directory and navigate to the directory. 
```
mkdir exiftool
cd exiftool
```
Create an **images** folder using `mkdir images` and add the target .jpg images inside it.

> [!NOTE]
> This program is for .JPG and .TIFF format files only.

Install pip for python3 and Pillow (Pillow will not work if you have PIL installed).
```
sudo apt install python3-pip 
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade Pillow
```

Create an **exif.py** file and paste the code from the [EXIF TOOL](https://github.com/davidbombal/red-python-scripts/blob/main/exif.py) repository

run the following to execute the python script
python3 exif.py
Now, check the data of each image using `less exif_data.txt`



## PhoneInfoga
PhoneInfoga is an OSINT tool used to scan international phone numbers. It allows you to first gather basic information such as country, area, carrier and line type, then use various techniques to try to find the VoIP provider or identify the owner.



### ⚙️ Setup
Download the latest release of PhoneInfoga:
```
bash <( curl -sSL https://raw.githubusercontent.com/sundowndev/phoneinfoga/master/support/scripts/install )
```
Move directory:
```
sudo mv ./phoneinfoga /usr/local/bin/phoneinfoga
```
To check if PhoneInfoga is running properly:
```
phoneinfoga
```
Use the `scan` command with the `-n` (or `--number`) option:
```
phoneinfoga scan -n "+1 (555) 444-1212"
phoneinfoga scan -n "+33 06 79368229"
phoneinfoga scan -n "33679368229"
```
Special chars such as `( ) - +` will be escaped so US-based numbers can be used easily:
```
phoneinfoga scan -n "+1 555-444-3333"
```

For further help, you may refer to the 
* [PhoneInfoga GitHub](https://github.com/sundowndev/phoneinfoga) repository.
* [PhoneInfoga Website](https://sundowndev.github.io/phoneinfoga/getting-started/install/).

## Osintgram
Osintgram is an OSINT tool on Instagram. It offers an interactive shell to perform analysis on the Instagram account of any user by its nickname.

### ⚙️ Setup
Clone the repository:
```
git clone https://github.com/Datalux/Osintgram.git
```
Navigate to the directory:
```
cd Osintgram
```
In the *config* directory go to **credentials.ini** and add the username and password of your account.

<br>

Do the following steps to avoid any runtime errors.

> [!IMPORTANT]
> * In the *Osintgram* directory, open **main.py** and replace every ***gnureadline*** keyword with ***readline***.
> * Then, go to the *src* directory open in **Osintgram.py**. Comment the *line 61* which reads ***self.following = self.check_following()*** to ***#self.following = self.check_following()***.

<br>

Create a virtual environment for this project:
```
python3 -m venv venv
```
Load the virtual environment:
```
source venv/bin/activate
```
Install the requirements for Osintgram:
```
pip install -r requirements.txt
```

Run the following to start the tool:
```
python3 main.py <target_username>
```
Use `list` to list down the commands available to use in Osintgram.

For further help, you may refer to the [Osintgram](https://github.com/Datalux/Osintgram) repository.

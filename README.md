# HAL13ERD

<br>

## Description

HAL13ERD is a Kali virtual machine created with the intent to gather various OSINT tools to perform basic OSINT investigations. This project's objective is to replicate the once-known Buscador Virtual Machine by creating your version.

> [!NOTE]
> This project was only created for OSINT on dummy accounts for educational purposes.

## OSINT Tools

The following tools used in the project are listed below:
* Sherlock
* TheHarvester
* GHunt
* Social_mapper
* EXIF Tool
* PhoneInfoga
* Osintgram

## Sherlock
Sherlock, a powerful command line tool used to find usernames across many social networks.

### ⚙️ Setup
Write the following code to install the tool on Kali:

clone the repo
```
git clone https://github.com/sherlock-project/sherlock.git
```

change the working directory to sherlock
```
cd sherlock
```

install the requirements
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
Clone the GHunt repository and move into the directory:
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
$ ghunt email <email_address> --json user_data.json
```


For further help, you may refer to the [GHunt](https://github.com/mxrch/GHunt) repository.


## Social_mapper
Social Mapper 

### ⚙️ Setup
Write the following code to install the tool on Kali:
```
```
Use ``

For further help, you may refer to the [social_mapper](https://github.com/Greenwolf/social_mapper) repository.



## EXIF Tool
EXIF Tool is a platform-independent command-line application for reading, writing, and editing meta information in a wide variety of files. This script version is created by David Bombal.

### ⚙️ Setup
Write the following code to install the tool on Kali:

Create a new EXIF Tool directory and move inside it. 
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
PhoneInfoga

For further help, you may refer to the [GHunt](https://github.com/mxrch/GHunt) repository.

### ⚙️ Setup
Write the following code to install the tool on Kali:
```
```
Use ``


## Osintgram
Osintgram

For further help, you may refer to the [GHunt](https://github.com/mxrch/GHunt) repository.

### ⚙️ Setup
Write the following code to install the tool on Kali:
```
```
Use ``

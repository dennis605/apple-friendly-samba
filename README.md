# Apple Friendly Samba
This bash script will create a samba share for you that will be visible in Finder and for Time Machine. Works on Ubuntu and Debian Linux.

## Preparation ##
To use this, you must first create a samba user. This command will create a new samba user:
```
sudo smbpasswd -a "username"
```
The username must be an existing user on the machine.

## How it works ##
The way the script works is by taking user input and modifying an existing _smb.conf_ file in this repository. Once it does that, it backs up the existing _smb.conf_ to _/etc/samba/smb.conf.bak_, and moves the modified _smb.conf_ file to _/etc/samba_.

## To use the script ##
After you've opened up a terminal, the first thing you're going to want to do is clone the repository to a convenient location.
```
cd ~/
git clone https://github.com/ADawesomeguy/apple-samba
```
Once you've done that, go into the folder and run _apple-samba-create_.
```
cd apple-samba
chmod +x apple-samba-create
./apple-samba-create
```
You will be prompted to enter your administrator password.

Once you've done that, answer a few prompts, and your share will be created!

## Adding new shares ##
To add new shares, simply run the _apple-samba-add_ script, and answer a few prompts along the way.
```
chmod +x apple-samba-add
./apple-samba-add
```

## Resetting samba ##
To reset Samba to default, just run the _apple-samba-reset_ script, which will back up the existing smb.conf file and replace it with the default smb.conf file.
```
chmod +x apple-samba-reset
./apple-samba-reset
```
Alternatively, you can run this command _**(NOT RECOMMENDED)**_:
```
sudo apt purge samba
sudo apt install samba
```

### Thanks for using this script! ###

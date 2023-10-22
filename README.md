# HTB_Sandworm
Walkthrough Hack The Box Sandworm

# IP: 10.10.11.218

# Step 1: Scanning

$ sudo nmap -sV (Version Detection) -sC (--script) -oN (Output File) nmap.txt 10.10.11.218

# Step 2: Adding Site to Host File (https://ssa.htb/) 

$ sudo nano /etc/hosts

Add 10.10.11.218  ssa.htb

And access the Host from browser

# Step 3:
$ sudo dirb https://ssa.htb

Then open https://ssa.htb/admin in Browser

# Step 4:

$ gpg --gen-key      // Generating Public Key

Real Name: {{7*7}}

Email: a@a.com

$ gpg --armor --export a@a.com > Public_Key.asc    //Exporting the Generated Public Key

## Making Payload Text File

$ echo "Test" > Payload.txt

## Creating a Signed Payload File (Signed_Payload.txt) from Payload.txt using Public Key previously created 

$ gpg --clear-sign --output Signed_Payload.txt Payload.txt


* Left the box

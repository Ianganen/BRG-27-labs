# BRG-27-labs
ISEA BRG27
Virtualisation & Linux Setup 
 Session 1a-1 (AM)
 Installing VMware Workstation
 Installing Ubuntu
 Setting up GitHub Account
Boot the VM using the downloaded ISO and install Ubuntu. 

Using Linux commands like apt install updates, apt install upgrade, apt install apache2 etc to set up Ubuntu
I learnt that the setup is extremely important and must be done correctly in order for your Linux to run smoothly as i experienced difficulty with the configuration of my settings resulting in unexpected errors when running my commnands. But with the feedback from my lecturer, i was able to rectify by resetting my Ubuntu by following the correct steps  and configuration.


Session 1a-2 (AM)
I learn how to use commands like ps -e,top,1 to monitor processes running in my Linux script. 

I learnt how to use ls, ls -la, ls -alt, ls -lah to explore the files I created for my lab activities.

I learnt how to create new fi;es in my Linux script using touch/ I edited and viewed its conetns using the it,nano, cat, less commands.

I learnt how to copy and move files with cp, mv; delete them with the rm commands.

I also learnt how to view system info using the uname -a, lsb_release -a, hostnamectl commands

As we move into the lesson,i learnt more about the inportant of having permissions to run certain commands and how to check if a user has those permission and how to add users in my Linux script by using whoami, sudo whoami to check for permissions to run certain commands.


I added users to my Linux script by using adduser with a regular user and also tried it  then with sudo, with the sudo command, i can run the script as a root user which is someone who has unlimited access within the system and learnt how other users; permission might be restricted with the help of the user related commands.

I was taught how to identify private IP using the command 'ip a' and how to ping local devices using  ping 8.8.8.8 or ping[address]

I learnt how edit and create custom aliases using /etc/hosts and how  to  test them  with ping, use nslookup and install/use whois to lookup domains like google.com

I learnt how to use lsusb, lspci, `less /proc/cpuinfo to access information on the hardward of my Linux system.

  I learnt to use commands to redirect output using for example, lsusb > output_of_lsusb, then view with less and cat.

 I installed apps via Ubuntu Software Centre by running commands like sudo apt update,sudo apt upgrade, sudo apt install vlc. 

 I used/etc/apt/sources.list directory to store additional configuration files, allowing for easier management of multiple repositories. 

 Session 1b-1
 Installing and configuring the Apache webserver.
 Launching Ubuntu Operating system. 
 Open a terminal
 Updating and installing apache and additional software using script
 sudo apt update
 sudo apt install apache2
 sudo apt install nmap
 sudo apt install openssh-server
 
 To find ethernet ip address
 use ip a

 Making changes to changes to the html of Apache web page
 use nano /var/www/html/index.html 

 Nmap is a port scanning tool and will tell you what ports are open on a machine connected to the Internet
 nmap [anotheripaddress]
 cannot be done if apache is installed

 UFW is the Ubuntu firewall (requires permission so sudo is used to run UFW commands)
 sudo ufw status verbose
 sudo ufw enable
 sudo ufw status verbose
 sudo ufw allow 80/tcp

This allows port 80 access.

SSH
SSH is a program that allows you to get command-line access to machines on the Internet. A username and password are required to access another machine. 
ssh [anotheripaddress]
Might fail due to no port access and might required manual opening ports required for ssh.

Create a new user
less /etc/passwd (check contents)
sudo adduser username
less /etc/passwd (contents have changed after adding new user)

SSH (part 2)
ssh [anotheripaddress]
ssh username@[anotheripaddress]
after making necessary changes type exit to leave
if it doesnt work try it again

Downloading books online
wget https://www.gutenberg.org/files/76/76-0.txt
wget file2
wget you get the idea ;)

Creating a directory called books with
mkdir books
move the 3 book files in directory next
tar cf books.tar books (create tar archive)
bzip2 books.tar (zip file)
ls -la
Compared the unzipped and zipped file
zipped file should be smaller

Use this to unzip the file

bunzip2 books.tar.bz2
tar -xvf books.tar

Session 1b-2
excerise to practice managin linux permission

Create three different users: 
Alice, Bob and Mallory. Create a directory called 'shared' in /home/. 
Create ten files inside it. 
Ensure that this folder has the User group and permissions to ensure that:

Alice can read, write and execute files
Bob can read and execute files, but cannot write to them
Mallory can neither read, write or execute files
To complete this, you will need to use group member

 Some of the commands below require sudo (permissions to run so take note)
 sudo
 ls [-l]
 groupadd
 adduser [bob] [awesomegroup]
 deluser [bob] [awesomegroup]
 less /etc/passwd
 less /etc/group
 delgroup
 chmod
 chown
 chgrp
 rm
 mkdir
 touch
 su [alice] [bob] [mallory] -s /bin/bash
 whoami

 Make sure you check the permissions from the perspective of the user you created.
 You must log in as that user. You can use the ''su'' command to switch between users and the ''whoami'' command to check your work. You may also want to use the '''-R''' flag, to
 recursively make changes
 chown -R
 chgrp -R

 Session 1b-3
 Download archive file from LMS
 extracting the file
 bunzip2 Gutenberg.tar
 tar -xvf Gutenberg.tar
 
 Searching for filenames
 find /path/to/where/you/search/from -name "*.extension"
 grep -r "string" /path
 Modification and creation dates
 find $1 -type f -exec stat --format '%Y :%y %n' "{}" \; | sort -nr | cut -d: -f2- | head
 find /path/to/where/you/search/from -type f -printf '%T+ %p\n' | sort | head -n 20
 find /path/to/where/you/search/from -type f -size 68c -exec ls {} \;
 find /path/to/where/you/search/from -type f -size +512k -exec ls -lh {} \;
 du -a /path/to/where/you/search/from | sort -n -r | head -n 20

Investigating the frequency of elements in a file
sed -e 's/\s/\n/g' < file_of_interest.txt | sort | uniq -c | sort -nr | head  -200

Session 2a-1
TCO (total cost of ownership)

Requirements and Assumptions
Costs will vary depending on the assumptions you make. So you need to be very explicit in your assumptions and apply them equally to alternatives you are considering.
For example, make sure certain variable stay the same to ensure equality in cost.

Gathering specifications and costs
With a list of expense items associated with your printers, you should now find the unit costs for all the items. the specification and needs of a certain item can determine if they require extra cost.

For example, you listed paper as a variable cost. You will be able to find the cost of paper the web. If you listed electricity as a cost you could visit the power company website to determine that cost of electricity. Sreach average electric price in that area where the item will be used.

Calculating Consumption
Using your assumptions you can calculate how much of each fixed and variable cost will apply for the period you are considering. For example, if we are looking at a 5 year period and we assume that we will print 400 pages per week then our total paper consumption will be 5 (years) x 52 (weeks) x 400 (pages) # 104,000 pages. From this number, we can work out how many other consumables we require. Calucate it accurately will determine the values you are working with.

Calculating cost
Knowing the number of consumables used over the time period and the cost of each individual consumable, determine the cost for each type of consumable and then add these to determine the total cost of ownership. Number of consumables can also affect cost of ownership as some items are more cost efficient when used in large groups for example licensing.

Session 2b-1

Login to Amazon EC2 
Launch Ubuntu using these steps
Launch a new instance (virtual machine)
Follow the steps on the AWS site.
Instance type - Pick a "free tier eligible" Ubuntu 20.04 Instance.
Configure the instance details - You can leave everything as the default.
Add storage - The default is to create a virtual machine with an 8GB hard drive. That's fine, leave it at the default.
Add tags - There is no need to add any tags so continue to "Configure Security Group".
Configure Security Group
Security group name - Call it "ssh-and-web"
There is an existing SSH permission that is needed to manage your remote server, that is fine.
Click "Add Rule" and select HTTP (web) as the type. This allows web requests to be received by our server.
Review and Launch
There may be a warning that your server is "open to the world". Anyone can attempt to join this server
If you are happy with the configuration, click "Launch".
Create a new "key pair". AWS uses key files rather than a username and password to verify your identity when logging into your virtual machine. If you lose this file it is unlikely you will be able to mange your virtual machine so it is important to keep it safe. Give it a meaningful name like "webserver-key" so that you can identify it later.
Launch Instance - Click on "Launch Instance" and your server will start. After this you can use "View Instance" to monitor it's progress.

Console Access to the Virtual Machine
Now that your server is running in the cloud you need to login to the command line of your virtual machine. If you select your virtual machine and click the "connect" button. Then click on SSH client and note the string provided.

Open Powershell, the Linux command line or the MacOS terminal on yur device. Then use 'cd' to move to the directory where you downloaded your key. Then you can paste the string that was provided to you above. It should look something like:
 ssh -i "yourkeyname.pem" ubuntu@ec2-12-123-1-35.ap-southwest-5.compute.amazonaws.com

 Install apache web server using 
 sudo apt update
 sudo apt install apache2


Edit index.html on the Webserver and test using
 nano /var/www/html/index.html

 Downloading files from the internet striaght to your machine in the cloud with wget
 wget http://www.eecs.berkeley.edu/Pubs/TechRpts/2009/EECS-2009-28.pdf
 
 This command should download the weekly reading into your /home/ubuntu directory. You would then need to move it into the /var/www/html directory using sudo. Try:
 sudo cp EECS-2009-28.pdf /var/www/html/

 Creating hyperlink using
 <a href="filename.pdf">Click here</a>
 
To complete using a directory and moving files to the correct directory
mkdir
mv

Session 2b-2
Basic Bash Linux commands
pwd	Displays the current directory path.
ls	Lists files and directories.
cd	Changes the current directory.
mkdir	Creates a new directory.
touch	Creates a new empty file.
cp	Copies files or directories.
mv	Moves or renames files or directories.
rm	Removes files or directories.
echo	Displays a line of text/string.
cat	Concatenates and displays file content.

Create a new directory
mkdir LabFiles
cd LabFiles

Create a new text file
touch notes.txt

Write Content to the File:
echo "This is a Bash scripting lab." > notes.txt

Display File Content:
cat notes.txt

Copy the File:
cp notes.txt backup_notes.txt

Rename the File:
mv backup_notes.txt old_notes.txt

Remove a File:
rm old_notes.txt
 
Creating and Executing Basic Bash Scripts
cd ~/LabFiles

Create a new script file
nano hello_world.sh

add the content in the script
BASH
#!/bin/bash
echo "Hello, World!"
Save and Exit:

Press CTRL + X, then Y, and ENTER to save the file. Make the Script Executable:
chmod 777 hello_world.sh

Execute the Script:

./hello_world.sh

nano hello_world.sh
Modify the echo Command:

echo "Welcome to the Bash scripting lab!"
Save and Execute:

./hello_world.sh


Create a New Script:

BASH nano system_info.sh

Create a New Script:

BASH nano system_info.sh

Add the Following Content:
#!/bin/bash

echo "System Information Script"

# Display current user
echo "Current User: $(whoami)"

# Loop through the next five numbers
for i in {1..5}
do
    echo "Iteration: $i"
    sleep 1s
done

# Conditional Statement
read -p "Enter a number between 1 and 10: " number

if ! [[ "$number" =~ ^[0-9]+$ ]]; then
    echo "Invalid input: Please enter a numeric value."
    continue
fi

if [ "$number" -le 5 ]; then
    echo "You entered a number less than or equal to 5."
elif [ "$number" -le 10 ]; then
    echo "You entered a number greater than 5 but less than or equal to 10."
else
    echo "Number out of range."
fi
Save and Make Executable:

chmod 777 system_info.sh
Run the Script:

./system_info.sh

Automating System Monitoring Tasks
Automate the monitoring of system resources such as CPU usage, memory usage, and disk space.

Create a New Script:

nano resource_monitor.sh
Add the Following Content:

#!/bin/bash

echo "System Resource Monitoring"

# Number of iterations
read -p "How many times would you like to monitor the system? " iterations

# Loop based on user input
for ((i=1; i<=iterations; i++))
do
    echo "----- Monitoring $i -----"
    
    # Display CPU usage
    echo "CPU Usage:"
    top -b -n1 | grep "Cpu(s)"

    # Display Memory usage
    echo "Memory Usage:"
    free -h

    # Display Disk usage
    echo "Disk Usage:"
    df -h | grep "^/dev"

    echo "-----------------------"
    sleep 5s
done

echo "Monitoring complete."
Save and Make Executable:

chmod 777 resource_monitor.sh

Run the Script:

./resource_monitor.sh

  Session 3a-1 
  Use Amazon EC2
  you should ssh into the server and install the Apache webserver as follows:
  sudo apt install apache2
  
Obtaining and linking a domain name
Obtain a domain name from a Domain Name Registrar such as AWS Route 53, Namecheap, CloudFlare, Godaddy). Avoid leaving your credit card details or auto-renew on your domain name if you do not plan to use this domain name after this unit. With some providers, this is not possible. If this is the case, remember to terminate your account at the end of the semester. Paying with Paypal might be an option.

After you have purchased your domain name, you want to link it to your cloud machine. The most straightforward strategy from here is to create an A record pointing to your cloud-based machine's Public Internet-facing IP address. After these changes have been made, sometimes it will take a few hours for the DNS changes to propagate throughout the Internet. You should not proceed until you can verify that the domain name entered in a web browser URL goes to your website.

Testing
Can you now browse to the website? Can you enter your domain name into a browser and reach your page? If not, troubleshoot.

Is the domain resolving correctly? (ping, nslookup) - Note: ping will not be successful unless a rule for ICMP has been added to the Security Group for your AWS Instance


Session 3a-2
Before proceeding, make sure your domain has an A record pointing to your server’s IP address. To confirm this setup, try connecting via SSH from your local machine using:

bash
Copy
Edit
ssh -i pemkey.pem ubuntu@[your-domain-name.com]
This guide assumes you're using the Apache web server and have access to it. To check if it's working, open your domain in a web browser or run:

bash
Copy
Edit
wget http://[your-domain-name.com]
If either of these tests fails, revisit the Amazon EC2 and DNS configuration labs to ensure everything is set up correctly. Also, confirm that ports 22, 80, and 443 are open in your EC2 security group.

Getting an SSL Certificate from Let's Encrypt
For testing, ensure ports 22, 80, and 443 are accessible through your firewall. After confirming your website is accessible over HTTP (port 80), you can obtain a free SSL certificate and enable HTTPS (port 443).

Go to https://certbot.eff.org and choose Apache and Linux (snap) as your software and system. Follow the provided instructions in your terminal.

Once complete, open your website in a browser and check for the padlock icon in the address bar. Click it to view details about the certificate issuer

Session 3b
Hello World!
Try running the following code.

 #!/bin/bash
 # This is a bash comment 
 echo "Hello Bash World!"
 Giving Permissions and Running Your Script
Start by saving your script file (e.g., somecode.sh) using a text editor. Then, grant it execution permissions:

bash
Copy
Edit
chmod 777 somecode.sh
You can now run it with:

bash
Copy
Edit
./somecode.sh
Using Variables in Bash
Update your script to include variables like this:

bash
Copy
Edit
a="Hello bash using variables"
echo $a
Make sure you understand how variables work before continuing.

Performing Basic Calculations
To do simple arithmetic in Bash, try:

bash
Copy
Edit
a=10
b=5
c=$((a + b))
echo $c
Experiment by modifying this example to try subtraction (-), multiplication (*), and division (/) so you become comfortable with different operations.

Editing a Loop
Take this sample loop:

bash
Copy
Edit
#!/bin/bash
for ((i=0; i<10; i++)); 
do 
  echo $i
done
Modify it to calculate and display the sum of all numbers from 0 to 9.

Creating Files and Folders for Backup
In /home/ubuntu/Documents, create test files and directories:

bash
Copy
Edit
touch file1 file2 file3 file4 file5
mkdir testfolder
cd testfolder
touch file11 file22 file33 file44 file55
These serve as the data you'll back up.

Writing the Backup Script
Now, write a script that copies everything from /home/ubuntu/Documents into /home/ubuntu/backup. Use a text editor:

bash
Copy
Edit
nano /home/ubuntu/testscript
Inside the script, write each command on a new line. Don't forget to create the /backup directory first if it doesn’t exist.

Make the script executable and run it:

bash
Copy
Edit
chmod 777 /home/ubuntu/testscript
./testscript

Making the Script Globally Accessible
To make the script usable by all users, move it to /usr/bin:

bash
Copy
Edit
sudo mv /home/ubuntu/testscript /usr/bin/testscript
sudo chown ubuntu /usr/bin/testscript
Now, test it by running:

bash
Copy
Edit
testscript
Linux finds it automatically via the $PATH. You can check your system paths with:

bash
Copy
Edit
echo $PATH
Archiving Your Backup
To improve your script, zip the backup and name it with the current date. Add this:

bash
Copy
Edit
now=$(date +"%d_%m_%y")
zip -r "$now.zip" /home/ubuntu/backup/*
mv "$now.zip" /home/ubuntu/
This will create a zipped backup named with the current date.

Automating with Cron
Edit your system’s crontab:

bash
Copy
Edit
sudo nano /etc/crontab
Add a line like this to run the script hourly:

bash
Copy
Edit
# m h dom mon dow user command
  9 * *   *   *   ubuntu /usr/bin/testscript
Power Management (Optional)
Pause and consider how your system could save energy. Try using suspend or hibernate modes locally (not on a cloud VM) to automatically sleep from 6 PM to 6 AM.

Uploading Backups to the Cloud
Once your script zips the backup, you can transfer it to a cloud server using:

bash
Copy
Edit
scp -i [your_pem].pem [filename.zip] ubuntu@[your-server-IP]:/home/ubuntu/
For the script to work via cron, make sure full paths are used and that you’ve accepted the SSH certificate by connecting manually once:

bash
Copy
Edit
sudo ssh -i yourkey.pem ubuntu@your-server-ip
Final Script Example
bash
Copy
Edit
now=$(date +"%d_%m_%y")
cp -R /home/ubuntu/Documents/* /home/ubuntu/backup/
zip -r $now.zip /home/ubuntu/backup/*
cp $now.zip /home/ubuntu/
scp -i /home/ubuntu/yourkey.pem $now.zip ubuntu@your-server-ip:/home/ubuntu/


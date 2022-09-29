Environment Setup
We will be using the SEED Labs virtual machine (Ubuntu 20.04), you can follow the instructions hereLinks to an external site. to setup the environment.

Local Setup for Linux/macOS
Download and install the latest version of virtualbox at https://www.virtualbox.org/wiki/Downloads
Download the SEED Labs virtual machine at https://drive.google.com/file/d/138fqx0F8bThLm9ka8cnuxmrD6irtz_4m/view?usp=sharingLinks to an external site.
Build from Scratch
You can also build the VM from scratch, following the instruction hereLinks to an external site.. If you're using VirtualBox, I also recommend using vagrant to download the base system.

Download and install the latest version of vagrant at http://www.vagrantup.com/downloads.html
Add guest VM
# download a 64-bit VM
[host] $ vagrant box add ubuntu/focal64
==> box: Loading metadata for box 'ubuntu/focal64'
    box: URL: https://atlas.hashicorp.com/ubuntu/focal64
==> box: Adding box 'ubuntu/focal64' (v20211026.0.0) for provider: virtualbox
    box: Downloading: https://atlas.hashicorp.com/ubuntu/boxes/focal64/versions/20211026.0.0/providers/virtualbox.boxLinks to an external site.
==> box: Successfully added box 'ubuntu/focal64' (v20211026.0.0) for 'virtualbox'!

# move to your working directory
[host] $ mkdir cs255
[host] $ cd cs255

# initialize the VM
[host] $ vagrant init ubuntu/focal64
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.

Modify the Vagrantfile according to assign a minimal of 2G memory (vb.memory), then start the VM.
# launch!
[host] $ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'ubuntu/focal64'...
...

[host] $ vagrant ssh
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-91-generic x86_64)
...
vagrant@ubuntu-focal:~$
Install 32-bit libraries and software necessary to the labLinks to an external site..
# in case you cannot run the challenges
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 gcc-multilib
Local Setup for Windows
If you are using Windows, I would recommend using WSL2.

Windows 10: install the Windows Subsystem for Linux https://docs.microsoft.com/en-us/windows/wsl/install-win10
Windows 10 (optional): install Windows Terminal https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701
Then follow the build from scratch steps above to finish the setup.
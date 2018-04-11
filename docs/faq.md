# FAQ

1. __Can I change the location where virtual machines are stored?__

    Yes, this is set within VirtualBox preferences. The default location is:
       * Windows: C:\Users\USERNAME\VirtualBox VMs
       * Mac OS X and Linux: ~/VirtualBox VMs

2. __Can I change the location where box files are located?__

    The environment variable VAGRANT_HOME can be set to change the directory where Vagrant stores global state. By default, this is set to ~/.vagrant.d. The Vagrant home directory is where things such as boxes are stored so that it can become quite large on disk.

    Usually, this location is by default set to:
    * Windows: C:/Users/USERNAME/.vagrant.d/boxes
    * Mac OS X and Linux: ~/.vagrant.d/boxes

3. __How many machines can I have 'RUNNING' at the same time?__

    It depends on the size of your local machine. The more RAM you’ve got, the bigger the number of Qlik Machines you can run at the same time (in RUNNING state). It’s recommended not have more than 3/4 as an average. However, you can have as many as you like if they are SUSPENDED or POWEROFF.

4. __I want to access Windows of a specific scenario, how do I do it?__

    You can only access Windows for already provisioned scenarios.
    Open VirtualBox application and double click on the virtual machine you like to access. You'll access Windows logged-in as 'vagrant' user.

5. __QMI seems to take quite a lot of disk space!, what should I do?__

    FAQ 1 and 2 help you change the location where Qlik Machines and boxes are stored.

6. __VT-x is disabled in BIOS.__

    If you get an error saying "VT-x is disabled in BIOS" (or similar) that means Virtualization Technologies are disabled in your machine and you won't be able to run virtual machines in it.

    You can change this setting by entering BIOS at reboot. If you don't feel confident enough to change this setting yourself, please contact IT.

7. __Should I let Virtualbox or Vagrant updates?__

    The critical thing to check is compatibility between VirtualBox and Vagrant.
    * Vagrant 2.0.2
    * VirtualBox 5.1.26
    Updating or using newer versions shouldn't break QMI but do so at your risk, :-)

8. __Error while provision: The ‘reload’ provisioner could not be found__

    Some scenarios need specific plugins to be installed prior provision. To list currently installed plugins, type the following in a terminal window.

    vagrant plugin list
    Make sure vagrant-reload, reload, vagrant-windows-sysprep and vagrant-disksize are on the list. If any of them doesn't show up type the following to install:

    vagrant plugin install vagrant-reload reload vagrant-windows-sysprep vagrant-disksize
    It may also rarely happen while installation of plugins you end up getting errors resolving dependencies. This command re-installs all currently installed plugins resolving those dependencies:

    vagrant plugin expunge --reinstall

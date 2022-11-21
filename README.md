# 2420_week11_Lab

#### Robeen, Cloue

# Starting Off

To begin download our repo which includes 4 files for backups

- backup-service

- readtest

- backup-service.service

- backup-service.timer

## SSH

1. Generate key-pair using `ssh-keygen`

2. Copy the contents of `<keygen>`.pub to ~/.ssh/authorized_keys in your backup sever

3. Write down the name of the key from `<keygen>` for later use

## Script file Placement

We will start with backup-service and readtest.

  1. `cd` into `~/opt/`

  2. Create a folder called `backup-script` using `mkdir`

  3. Place the file `backup-script` and the `readtest` in that folder using `mv`

  4. Add execution permissions using `chmod +x backup-script` 

## Editing readtest

readtest is the file that is used by the script in order to backup.

looking at readtest:

![readtest file](/images/readtest.png)

we see two thing:

  1. IP in the *first line*

  2. An example file/directory
  
you can edit the file as you like but if the location of the file does not work the script won't either! becuase IP is firstline and everything else has to be pathed corectly

## Service & Timer Placement

now we will place & enable our `.service` and `.timer` files

they look like this

![readtest file](/images/Timer.png) ![readtest file](/images/Service.png)

  1. `cd` into `/etc/systemd/system/`

  2. `mv` the `backup-service.service` & `backup-service.timer` into the `/etc/systemd/system/`
  
  3. Run the command `sudo systemctl daemon-reload`

  4. Enable the service file with `systemctl enable backup-service.service`
  
  5. Enable the timer file with `systemctl enable backup-service.timer`
  
  6. Verify that they **both** are working with `systemctl status backup-service.service` & `systemctl status backup-service.timer`
  
  7. A successful case of this looks like:
 
  ![systemctl status output good](/images/timer.png)
  
  8. Congrats you are done!

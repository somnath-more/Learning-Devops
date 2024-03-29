## Systemand Service Management
Create Your own systemD Service
- Systemd is a Linux initialization system and service manager that includes features like on-demand starting of daemons, mount and automount point maintenance etc.
Systemd also provides a logging daemon and other tools and utilities to help with common system administration tasks.

- What is a service unit?
A file with the .service suffix contains information about a process which is managed by systemd. It is composed by three main sections:

1.Unit
The Unit section of a .service file contains the description of the unit itself, and information about its behavior and its dependencies: (to work correctly a service can depend on another one). Here we discuss some of the most relevant options which can be used in this section

First of all we have the Description option. By using this option we can provide a description of the unit. The description will then appear, for example, when calling the systemctl command, which returns an overview of the status of systemd.

Secondly, we have Documentation option. By using this option we can get the details of the service and documentation related to it.

By using the After option, we can state that our unit should be started after the units we provide in the form of a space-separated list.

[~]$ cat /etc/systemd/system/project-mercury.service
[Unit]
Description=Python Django for Project Mercury
Documentation=http://wiki.caleston-dev.ca/mercury
After=postgresql.service
2.Service
In the Service section of a service unit, we can specify things as the command to be executed when the service is started, or the type of the service itself.

[Service]
ExecStart=/usr/bin/project-mercury.sh
User=project_mercury
Restart=on-failure
RestartSec=10
3.Install
This Install section contains information about the installation of the unit

[Install]
WantedBy=graphical.target
How to Start the Service now ?
The system to detect the changes you have done in the file, we need to reload the daemon and start the service.
```bash
systemctl daemon-reload
```
``` bash
 systemctl start project-mercury.service
```

systemd:
### Difference between systemd and systemCTL
- systemd is a system and service manager for Linux operating systems. It is designed to replace the traditional SystemV init system.
- It is responsible for initializing the system, managing system processes, and acting as a central management and configuration point.
systemd is responsible for process management, logging, device management, and more.
systemctl:

- systemctl is a command-line utility that is part of the systemd system and service manager.
It is used to examine and control the systemd system and service manager. You can use it to query the status of services, enable or disable services, start or stop services, and more.
- Common systemctl commands include start, stop, restart, enable, disable, and status for managing services.
- In summary, systemd is the underlying system and service manager, while systemctl is a command-line interface to interact with and control systemd. The combination of both provides a comprehensive way to manage services and the system on Linux.
![Alt text](<Screenshot from 2024-02-25 15-34-57.png>)
#### Here, the service command is used instead of the systemctl command and it worked out absolutely fine.
![Alt text](<screenshots/image-28.png>)

- The service
![Alt text](<screenshots/image-45.png>)

Creating Custom Service:
Create a Service Unit File:

Service unit files are typically stored in the /etc/systemd/system/ directory and have a .service extension. 

Create a new file, for example, my_custom_service.service:

bash
``` bash
sudo nano /etc/systemd/system/my_custom_service.service
```

Copy code



Description: A human-readable description of the service.
After: Defines when the service should be started in relation to other units (e.g., network.target).
ExecStart: Specifies the command or script to start your custom service.
Restart: Configures how the service behaves when it exits.
WantedBy: Specifies the target that should be reached to start this service.

System ctl and journactl
![Alt text](<screenshots/image-29.png>)
 * journalctl: used maximum in troubleshooting

 ![Alt text](<screenshots/image-12.png>)

- The systemctl daemon-reload command is used to reload the systemd system manager configuration. This command is necessary when changes have been made to the systemd unit files (service, socket, target, etc.), and you want systemd to recognize these changes without restarting the entire system
 ``` bash
 systemctl daemon reload
 ```


The systemctl edit command is used to create or edit drop-in units for a given service. Drop-in units allow you to override or extend configuration settings for an existing service without modifying the original service unit file. Here's a simple example using the Apache web server (apache2 service):

``` bash
sudo systemctl edit apache2 --full
``` 
Some more usefull Command about systemctl:

![Alt text](<screenshots/image-44.png>)

## JournalCTL


- The **journalctl** command is used to query and display messages from the journal, which is a centralized logging system on Linux systems that use systemd. The journal contains information about various system events, including log messages from services, kernel messages, and other system-related activities. Here's an explanation of how to use journalctl
# docker_project_Sanjay-Tripathi

The project is to make our own cloud, to manage the personal data like photos,Videos,document etc.
With own cloud you pick a server of your choice, at home, in a data center or at a provider. And that is where your files will be. cloud runs on that server, protecting your data and giving you access from your desktop or mobile devices. Through cloud you also access, sync and share your existing data on that FTP drive at the office, a Dropbox or a NAS you have at home.

the images support multiple architectures such as x86-64, arm64 and armhf. i utilize the docker for multi-platform.

this is the command line code you can use in redhat  or centos8 to run:-
   ## docker create --name=nextcloud -e PUID=1000 -e PGID=1000 -e TZ=Europe/London -p 443:443 -v /path/to/appdata:/config -v /path/to                  /data:/data --restart unless-stopped      linuxserver/nextcloud
   
  # for docker-compose.yml
   make sure you have made the volume name config and data by cmd docker volume create nameOfVolume
   you can change port no. do not change port no of container 
                 version: "2.1"
                  services:
                       cloudoS:
                          image: linuxserver/nextcloud
                          container_name: homeCloud
                       environment:
                         - PUID=1000
                         - PGID=1000
                         - TZ=Europe/London
                       volumes:
                         - config:/config
                         - data:/data
                       ports:
                         - 443:443
                       restart: unless-stopped

after this you can access on your cloud by:-
                                          https://your_ip:443
                                          do not use http  use https






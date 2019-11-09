# Tortuga

## This tool can (only) be used to commit the abhorrent crime of violating the copyright of billionaires, by using it you could be prosecuted by your local authority, the author refuses to take any responsibility for actions performed using the provided tools and guide or consequences therefor.

An all-in-one docker based media server & content acquiring service.

## Preconfig

Run docker somewhere, get docker-compose installed, allow access to ports 443 and 80 on this host from either the entire internet or a whitelist of good addresses (this is safer but more hassle)

Then acquire a domain or subdomain and create an A record for a subdomain of * directed to the address of this machine

If you require assistance bother someone who knows the difference between DNS and DHCP.

**During the rest of this guide replace domain.name with your chosen domain or subdomain**

## Docker Compose

Initially run the docker compose file by cloning this repo and running

    docker-compose do the thing

This will download, create volumes for, assign the appropriate ports and run the docker containers for

1. qbittorrent - To download items
1. sonarr - To search for and maintain a list of desired TV shows
1. radarr - To search for and maintain a list of desired films
1. lidarr - To search for and maintain a list of desired music
1. jackett - To convert the requests from the \*arr services to HTTPS requests to torrent sites
1. plex - To play all of the *acquired* media
1. traefik - For management of HTTPS and routing
1. portainer - To manage the docker instance and because if you're using this you're probably not a docker expert who wants to learn all the arguments and flags.


If you already have services running in docker and don't want someone to come alone and mess the whole operation up, you're probably smart enough to modify the compose file as needed.

## Configuring each service
Each service is running either from its default provider or alternatively the well respected linuxserver.io provider.

### portainer
visit https://admin.domain.name

You will be provided the below page:

**Create a new and unique password and username combination for this service**, if you reuse a password utilised elsewhere and that service leaks your password or a weak password, there is a remarkably high risk that an attacker will be able to gain access to this service and use it to control the machine running docker. They may then be able to modify traffic inside your local network assuming you host the services in your home, this can provide the attacker with access to modify communications between yourself and any external service (which doesn't utilise HSTS) via arp spoofing attacks and modification of DNS requests. This would be bad. **You have been warned** letting attackers into your lan is bad and may result in tears and financial ruin.

Once you have created a password, you may login and see all the running services, you can add new services or remove them at will, it's pretty neat. Portainers parent organisation are currently burning VC money [citation needed] and want you to buy premium services, you shouldn't need them and don't rely on Portainer to manage docker should you wish to become hacker leet pro.


### qbittorrent
visit https://torrent.domain.name
login with the following credentials: admin/adminadmin

#### Change the password by clicking :

#### Create three catagories by clicking:

This is the service we will be using to download all of your media

### jackett

### sonarr

### radarr

### lidarr

### traefik

### plex

The author does not accept payment for this service however private tracker invites can be mailed to tortuga@nannal.com

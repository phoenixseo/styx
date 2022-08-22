# styx
Local LAMP in rootless Podman-Containers. Apache 2.4 + PHP 7.4 + PHP 8.1 + PHPMyAdmin + Redis + MariaDB

# Podman-Compose Container
Rootless Podman Containers with Apache 2.4 && PHP 7.5 && PHP 8.1 (in parallel, separated by Port).

# Start
cd /styx
podman-compose up -d
Will run the whole thing.
Web-Content in files/www... will run at Port 8080 AND 8088 in parallel.

# Stop
cd /styx
podman-compose down
Stopps all running Containers.

# Why?
At Time of this writing, PHP changes its Version from 7.4 to 8.0 / 8.1 on all Hosted Webservers.
I needed a local mass-hosting Development Environment to test Client Websites on Errors if PHP changes to 8/8.1.
I can simply download all client's Websites at once and let them run under PHP 7.4 && PHP 8.1 in parallel, simply by changing the Portnummber from 8080 to 8088.
Many of the Websites are updated via Composer, which can be quite difficult, if CMS Version changes in addition to the PHP Version.
This is my little cozy Development Environment to test and update.

# DNS Server
Not included is a DNS Server that resolves your internal IP to "*.sites.test". There are many ways to get this working: DNSMasq, Bind9, Unbind, ... The simplest way for me was to switch the included DNS Server on my NAS on.
DNS juggling can be very frustrating, if you do it with BIND9 oder Unbind, make sure you have someone you can ask why "this does not work".

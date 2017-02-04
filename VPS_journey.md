# My journey through a VPS

1. Obtaining it
    - Through Digital Ocean (student credit)
    - Ubuntu 16.04 (Because it was the default option and seemed like the most popular and hence most easy to learn from)

2. Connecting it to my domain
    - I obtained the domain ages ago through godaddy
    - had to set the CNAME? addresses of Digital Ocean on godaddy
    - made sure that I set the CNAME options on the DO droplet to catch all sorts of typos and stuff

3. Setting up apache
    - as simple as ```sudo apt-get apache2 install```
    - and then learning that ```systemctl start|stop|restart|status apache2``` are basically all the commands I will need to know

4. Setting up an SSL certificate  
    - I had a free one from NameCheap but didn't really wat to go the proprietary (read: easy) route because I tend to exhibit masochistic tendencies.
    - Let'sEncrypt is a FOSS certificate thingy, which is surprisingly giving CErtifiactes for free as long as you can verify that the IP address you want is, indeed, yours. Easily done with Certbot.
    - The Certbot page is easy enough to follow.

5. Redirection of traffic
    - Once you have a certificate, you need to redirect all your traffic to a secure port. This is the hard part.
    - Your config files are stored in /etc/apache2/sites_available/
    - You need to edit the config file to force all traffic to redirect to port 443. One line is all. Not sure if it's smooth as of yet, need to figure out why.

6. Cron Jobs
    - LE certs expire in a week, so you need to automate renewing it.
    - introduction to cron is brilliant to understand what to do
    - Google gives you huge elaborate scripts. Mine had two lines.
    - I didn't set a crontab, I put the script in /etc/cron.daily instead

7. Firewall
 -     

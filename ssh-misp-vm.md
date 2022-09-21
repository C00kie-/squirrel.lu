# How to access MISP vm from the OUTSIDE (virtualbox), but stay on your laptop still

## SSH

sudo systemctl status ssh
sudo systemctl enable ssh --now
sudo systemctl status ssh

## Virtualbox settings

Network > Adaptater[number]
  Attached to NAT
    Advanced
        check : cable connected and allow Port Forwarding, if it not configured by default by VB:
            NAME:ssh
            Protocol: TCP
            Host Port: 2222 or another
            Guest Port: 22
            
 ## SSH your vm
 
 from the host:
 
 ssh -p 2222 [user]@localhost

 
 

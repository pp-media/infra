# TODOs
* find out how we want to allocate the resources we have, we currently have 7 nuc style computers with both 4th gen and 10th gen intel and 16-64 gb ram
* set up base OS and develop a name standard
* start tinkering with ansible to create automation
* test ingestion and transcoding
* test if caspar can run on one of these boxes
* futher automate with ansible, the goal is easy-to-deploy and maintain

* plan b?

# Infra todos
* Set up ufw for all devices with default ports
    - Block all ports but 22/tcp if the process has never been run before
* Get vault fixed
* Fastfetch from all the hosts - save locally to inventory
* VLAN config for hosts to enable WAN links
* DDNS for WAN address
* Disable radios (Wifi and BT)

## Follow-ups

* Make sure preseed for Debian only needs hostname as manual input
* Get tailscale setup in preseed fixed

## Ideas

* Use uis-01 as k3s node
* Use uis-03 as GFX playout (has two HDMI, could do key and fill)

# Port Forwarding

## Port Forwarding (Required)

The number one reason that users have issues getting their host running is port forwarding. By default, the host is on port `:9982`, but you should forward all ports from `:9981` to `:9984`. You can see if your host has forwarded its port from this website: [http://canyouseeme.org/](http://canyouseeme.org)

{% hint style="warning" %}
Be sure to not forward port 9980, as this can represent a security threat. You'll need to access your router's manual to learn how to set up port forwarding on your device.
{% endhint %}

### What each port does

* :9981 (consensus p2p network)
* :9982 (renter-host-protocol-v2)
* :9983 (rhp-v3)
* :9984 (rhp-v3-websocket)

If your port is not forwarded, it's probably because your router does not support UPnP. Unfortunately, that means you need to go into the configuration yourself and do it manually. There are some great guides to help you here: [https://portforward.com/](https://portforward.com)

Renters know to contact your host from the network address in the host announcement. If your IP address has changed since your announcement, you will need to announce again. If you have a firewall or some networking setup that may be blocking inbound connections from the internet, you need to make sure that it allows traffic to reach the host.

Finally, if you have a dynamic IP address, you should strongly consider setting up something like DynDNS, which allows you to announce a hostname and then manages the dynamic IP address issue for you.

##

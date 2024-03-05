## NAT 
just like your home network with a wireless router  ,then vm will be assigned in a seprate subnet

Your vm can acess outside network like your host ,but no outside acess to your vm directly ,its protected
dhcp is internal

## Bridged
your vm will be in the same network as your host
it can be acessed by all computers in your host network
dhcp is external

## Host Only Network
Host only network creates a network that is compltely contained within host computer
This means that all vms connected to a host-only-n will be be visible
to the host and each other

## LAN segments

DEVICES:
Router (1941 Router0)
2 Switches (2960-24TT Switch0, 2960-24TT Switch1)

Switch0:
PC1 (PC-PT PC0, 168.90.0.2)
PC2 (PC-PT PC1, 168.90.0.3)
Laptop-PT (Laptop0, 168.90.0.4)
PC4 (PC-PT PC4, 168.90.0.5)

Switch1:
Server-PT (Server0, 210.3.14.2)
Server-PT (Server1, 210.3.14.3)
PC3 (PC-PT PC2, 210.3.14.4)
PC5 (PC-PT PC3, 210.3.14.5)

Explanations of commands:

CONFIGURING THE ROUTER INTERFACE:

"enable" - Enters EXEC mode on the router for advanced configuration.

"configure terminal" - Enter global configuration mode.

"interface GigabitEthernet0/0" - Selects interface GigabitEthernet0/0 for configuration.

"ip address 168.90.0.1 255.255.255.0" - Assiogns IP address and the subnet mask to the iterface we just selected, in this case "GigabitEthernet0/0".

"no shutdown" - Activates the interface.

"exit" - Exit the configuration mode.

"interface GigabitEthernet0/1" - Same as before. Selects interface GigabitEthernet0/1 for configuration.

"ip address 210.3.14.1 255.255.255.0" - Now assigns IP address also with subnet mask to the interface we just selected.

"no shutdown" - Activates the interface(again).

"exit" - Exit the configuration mode(again).

ENABLING DHCP FOR EACH NETWORK:

"ip dhcp pool NET1" - Creates a DHCP pool(Pool is a range of IP Addresses that can be assigned) with the name "NET1" for the first network.

"network 168.90.0.0 255.255.255.0" - Just puts a specific IP Address range for the DHCP pool.

"default-router 168.90.0.1" - Sets the default gateway for devices receiving IP addresses in this network.

"ip dhcp pool NET2" - Creates a DHCP pool(Pool is a range of IP Addresses that can be assigned) with the name "NET2" for the second network.

"network 210.3.14.0 255.255.255.0" - Just puts a specific IP Address range for the DHCP pool(for the second network).

"default-router 210.3.14.1" - Sets the default gateway for devices receiving IP addresses in this network(once again, for the second network).

After all these commands I just had to enable the DHCP Gateway on the end devices.

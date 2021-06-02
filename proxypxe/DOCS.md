# Home Assistant Add-on: ProxyPXE

## Installation

Follow these steps to get the add-on installed on your system:

1. Navigate in your Home Assistant frontend to **Supervisor** -> **Add-on Store**.
2. Find the "ProxyPXE" add-on and click it.
3. Click on the "INSTALL" button.

## How to use

The add-on has a couple of options available. For more detailed instructions
see below. The basic thing to get the add-on running would be:

1. Start the add-on.

## Configuration

The ProxyPXE add-on can be tweaked to your likings. This section
describes each of the add-on configuration options.

Example add-on configuration:

```yaml
DHCPserver: 192.168.1.1
TFTPpath: '/tftp'
MACROOT: false
dhcpoption:
  - vendor:PXEClient,6,2b
dhcpvendorclass:
  - set:BIOS,PXEClient:Arch:00006
  - set:UEFI,PXEClient:Arch:00007
dhcpboot:
  - tag:UEFI,grub/bootx64.efi
```

### Option: `DHCPserverIP` (required)

The IP address of the DHCP server in your network.

### Option: `TFTPpath` (required)

The path to the TFTP root directiory inside the config directiory of homeassistant.

#### Option: `MACROOT`

Use a different directory with bootloaders for each macadress. If enabled the path would look like this:
`tftproot/macadressofpc/pxebootfiles`

#### Option: `dnsmasqoptions`

Additional options put into dnsmasq config. Look into documationion for DNSmasq for more information.


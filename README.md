[![PyPi Version Alt](https://badge.fury.io/py/cisco_anyconnect_cli.svg)](https://pypi.org/project/cisco_anyconnect_cli/)  

# cisco_anyconnect_cli
Cisco AnyConnect client command line with KeePass support

# Installation
KeePassHTTP Plugin is required
vpncli.exe from Cisco AnyConnect Secure Mobility Client is required  
`pip install cisco_anyconnect_cli`

# Usage
```
Usage: anyconnect [OPTIONS] COMMAND [ARGS]...

  Connect to Cisco AnyConnect VPN Gateway

  I need vpncli.exe and will search in:

  - Current working directory
  - C:\Program Files (x86)\Cisco\Cisco AnyConnect Secure Mobility Client
  - C:\Program Files\Cisco\Cisco AnyConnect Secure Mobility Client"
  - In -p/--path given to the command (as file or directory)
  - In CISCO_ANYCONNECT_HOME environment variable
  - Availability in PATH variable

Options:
  -p, --path PATH  Directory or path to vpncli.exe
  -h, --help       Show this message and exit.

Commands:
  connect     Endpoint address
  disconnect  Disconnect
```

## Connect
User and password will be fetched from Keepass if no user is given
```
Usage: anyconnect connect [OPTIONS] URL

  Endpoint address

Options:
  -u, --user TEXT      Give username instead of KeePass lookup
  -p, --password TEXT  Give password instead of KeePass lookup
  --help               Show this message and exit.
```

# Examples
```
Entry in KeePass must be named or have a configured URL equal vpn-server-url.
$ anyconnect connect vpn.example.com

Without KeePass 
$ anyconnect connect vpn.example.com -u user -p pass

$ anyconnect disconnect
```

# Changelog
## v0.1
- Initial version with basic features
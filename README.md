# Privex CLI Domain Record Scanner

![GitHub last commit](https://img.shields.io/github/last-commit/Privex/scandomain)

A bash tool to make querying multiple record types / multiple domains from the CLI much easier, with the ability to display the records
in several different formats.

This tool wraps `dig`, if you don't have `dig` installed, it's usually available under the package name `bind-tools` or `dnstools` in
most OS package managers.


![Screenshot of scandomain commands](https://i.imgur.com/P3vygTz.png)


```text

    +===================================================+
    |                 © 2023 Privex Inc.                |
    |               https://www.privex.io               |
    +===================================================+
    |                                                   |
    |        ScanDomain tool                            |
    |        License: X11/MIT                           |
    |                                                   |
    |        Core Developer(s):                         |
    |                                                   |
    |          (+)  Chris (@someguy123) [Privex]        |
    |                                                   |
    +===================================================+

    ScanDomain tool - A bash tool (wraps 'dig') to make querying multiple record types / domains at once easier
    Copyright (c) 2023    Privex Inc. ( https://www.privex.io )

```

## Quickstart

```sh
# Via wget
wget -O /usr/local/bin/scandomain https://github.com/Privex/scandomain/raw/master/scandomain
# Via curl
curl -fsSL https://github.com/Privex/scandomain/raw/master/scandomain -o /usr/local/bin/scandomain

# Make it executable
chmod +x /usr/local/bin/scandomain

# Run it :)
scandomain privex.io
scandomain --help
```

## Install

### Dependencies

 - Bash (4.x recommended - standard on Linux systems, not standard on BSD systems)
 - `dig` (can be found in the package `bind-tools` or `dnstools`)

For debian/ubuntu based systems:

```sh
apt update
apt install bind-tools
```

For FreeBSD and some other BSDs:

```sh
pkg install bash bind-tools
```

For macOS:

```sh
brew install bash bind-tools
```

### Install directly into your bin folder using wget/curl

If you're able to write to /usr/local/bin:

```sh
# Via wget
wget -O /usr/local/bin/scandomain https://github.com/Privex/scandomain/raw/master/scandomain
# Via curl
curl -fsSL https://github.com/Privex/scandomain/raw/master/scandomain -o /usr/local/bin/scandomain

# Make it executable
chmod +x /usr/local/bin/scandomain
```

If you can't / don't want to install globally, you can install it locally into
your `~/.local/bin` folder - just make sure it's in your `PATH`:

```sh
# Via wget
wget -O ~/.local/bin/scandomain https://github.com/Privex/scandomain/raw/master/scandomain
# Via curl
curl -fsSL https://github.com/Privex/scandomain/raw/master/scandomain -o ~/.local/bin/scandomain

# Make it executable
chmod +x ~/.local/bin/scandomain
```

### Install by cloning the Git repo

Alternatively, if you prefer, you can clone the repo and install from the cloned Git repo instead.

This may be helpful if you want to use a specific tag, make it easier to update in the future
using `git pull`, or so you have the README and LICENSE on hand locally :)

```sh
git clone https://github.com/Privex/scandomain.git
cd scandomin

# If you're able to write to /usr/local/bin
install scandomain /usr/local/bin/

# If you can't / don't want to install globally, you can install it locally into
# your ~/.local/bin folder - just make sure it's in your PATH
install scandomain ~/.local/bin/

# If you don't have the 'install' command, you can simply cp it, just make
# sure to chmod +x it
cp -v scandomain /usr/local/bin/
chmod +x /usr/local/bin/scandomain
# Or install into your user bin folder:
cp -v scandomain ~/.local/bin/
chmod +x ~/.local/bin/scandomain

# Alternatively, you can run it straight from the repo folder!
./scandomain example.com
./scandomain --help
```

## Examples

View the built-in help, which includes usage examples, flags/switches/arguments, etc:

```sh
scandomain --help
```

Fetch the default record types (a aaaa ns mx soa txt) for privex.io

```sh
scandomain privex.io
```

Fetch the default record types (a aaaa ns mx soa txt) for privex.io in compact + quiet mode

```sh
scandomain -c -q privex.io
```

Fetch the default record types (a aaaa ns mx soa txt) for privex.io using nameserver 185.130.44.20

```sh
scandomain privex.io @185.130.44.20
```

Fetch just A + AAAA in flat mode for privex.io, google.com, and example.com

```sh
scandomain -f -r a,aaaa privex.io google.com example.com
```

Fetch just A + AAAA for example.com from nameserver 9.9.9.9 and validate + return DNSSEC record

```sh
scandomain -r a,aaaa +dnssec example.com @9.9.9.9
```

## License

OpenAlias.py is released under the X11 / MIT License, see `LICENSE` for more info.

## Thanks for reading!

**If this project has helped you, consider [grabbing a VPS or Dedicated Server from Privex](https://www.privex.io) -**
**prices start at as little as US$0.99/mo (we take cryptocurrency!)**

You can also donate cryptocurrency to us using our OpenAlias address `privex.io` :)

**Standard crypto donation addresses:**

```yaml
BTC: bc1q6tc5wutnm25uhvemq9x7602uaskt8f3jxfygmjurzl5nthc3pyuqkv9qp9
BCH: bitcoincash:qr6ss5pnnx9wad32j7lhulwp6k6we60gyuzsqc6pyj
LTC: MDRRb9pdLs6nXQ91VNfJEN68ohHSwWvscv
XMR: 85foJVKQTTihMoGWuC6Xm5XLktRWNHPjtb5vz7JmLays92jPbSQUxfE6AqK5pz6QanSJ6rV64pbmn85nFEzkb5fQCm2Q17P
ETH: 0x2e8687E5349f38e833F9111b25761B903902AdC0
DOGE: D9XEBJF55kN3XWEdDr5Z19GHMmgh7nrsEQ
HIVE/HBD: privex
EOS: privexinceos
```


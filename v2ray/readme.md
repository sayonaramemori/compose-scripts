### Quick start  
- Create the volume first.  
- Copy the config to the volume.
- Use it with privoxy or proxychains.  
```shell
sudo apt install -y privoxy proxychains

# For privoxy configuration
sudo vim /etc/privoxy/config

# Find this Line, Modify Default running port for Privoxy  
listen-address 127.0.0.1:10809

# Add this line below to receive http network stream and convert it to socks5 to v2ray
forward-socks5 / 127.0.0.1:10808 .

# Test using curl
curl -i google.com --proxy http://127.0.0.1:10809


# For proxychains configuration
sudo vim /etc/proxychains.conf

# Delete socks4 and add this line  
socks5 127.0.0.1 9000

# Test with github, not work for docker pull (deamon running)
proxychains git clone https://github.com/bhilburn/powerlevel9k.git
```


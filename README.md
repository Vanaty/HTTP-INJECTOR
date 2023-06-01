# HTTP-INJECTOR
## HTTP PROXY + PAYLOAD + SSH WS
### Installation
1. Install dependences.<br>
```bash
$ pkg install -y git openssh-client sshpass netcat-openbsd python3 & pip install configparser
```

2. Clone the repository.<br>

```bash
$ git colone https://github.com/Vanaty/HTTP-INJECTOR.git
```

3. Config your <code>setting.ini</code><br>
```env
[GENERAL]
socks5Port = 1080 #socks5://127.0.0.1:1080
ListenPort = 8080
Buffer = 4096
PROFILE = 1 #;1. PROFILE1#;2. PROFILE2 #;3. PROFILE3#;4. PROFILE4 #;5. -

[ssh]
host = us.myserveur.xyz
port = 443
username = myserveur-user
password = 123456
enable_compression = y

[PROFILE 1]
Proxy =  facebook.com:80
Payload = GET wss://sni_host/ HTTP/1.1[crlf]Host: [host][crlf]Upgrade: Websocket[crlf]Connection: Upgrade[crlf][crlf]

```

4. Run <code>inject.py</code>
```bash
$ python3 inject.py
```
5. Run <code>ssh.py</code>
```bash
$ python3 ssh.py
```
6. Add Socks5 proxy and Enjoy!
   <code>host: localhost/127.0.0.1 </code><br>
   <code>port: 1080 </code>

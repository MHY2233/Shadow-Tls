# Shadow-Tls
- **1.下载程序**

      wget https://github.com/ihciah/shadow-tls/releases/download/v0.2.25/shadow-tls-x86_64-unknown-linux-musl -O /usr/local/bin/shadow-tls && chmod +x /usr/local/bin/shadow-tls

- **2.写入配置文件**

```bash
[Unit]
Description=Shadow-TLS Server Service
Documentation=man:sstls-server
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
ExecStart=/usr/local/bin/shadow-tls --fastopen --v3 server --listen 0.0.0.0:8443 --server 127.0.0.1:12321 --tls gateway.icloud.com  --password JsJeWtjiUytremklO0oehf
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=shadow-tls

[Install]
WantedBy=multi-user.target
```
- **3.重载配置文件**

      systemctl daemon-reload

- **4.配置开机自启**

      systemctl enable shadow-tls.service

- **5.启动服务**

      systemctl start shadow-tls.service

- **6.查看服务状态**

      systemctl status shadow-tls.service



- **1.下载程序**

        wget https://github.com/ihciah/shadow-tls/releases/download/v0.2.25/shadow-tls-x86_64-unknown-linux-musl -O /usr/local/bin/shadow-tls && chmod +x /usr/local/bin/shadow-tls

- **2.写入配置文件**

        curl -Lo /etc/systemd/system/shadow-tls.service https://raw.githubusercontent.com/MHY2233/Shadow-Tls/main/shadow-tls.service && systemctl daemon-reload

- **3.重载配置文件**

        systemctl daemon-reload


- **4.配置开机自启**

        systemctl enable shadow-tls.service

- **5.启动服务**

        systemctl start shadow-tls.service


- **6.查看服务状态**

        systemctl status shadow-tls.service



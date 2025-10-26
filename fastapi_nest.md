```
journalctl -n 50 -f
```

```
[Unit]
Description=<STRING>
DefaultDependencies=no
After=network-online.target

[Service]
Type=simple
Restart=always
WorkingDirectory=/home/hs7t/<FASTAPIABLE DIR>
ExecStart=poetry run fastapi run --port <PORT>
TimeoutStartSec=0
Restart=always

[Install]
WantedBy=default.target
```

```
http://<SOMETHING>.hvii.cc {
        bind unix//home/hs7t/.<SOMETHING>.hvii.cc.webserver.sock|777
        reverse_proxy 0.0.0.0:<PORT>
        header Access-Control-Allow-Origin *
        header Access-Control-Allow-Methods *
        header Access-Control-Allow-Headers *
        @options {
                method OPTIONS
        }
        respond @options 204
}
```

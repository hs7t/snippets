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

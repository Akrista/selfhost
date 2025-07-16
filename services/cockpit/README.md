# Cockpit

[Documentation](https://cockpit-project.org/guide/latest/)
[Cockpit File Browser](https://github.com/cockpit-project/cockpit-files)

## Behind Traefik

Obtained from [here](https://community.traefik.io/t/cockpit-behind-traefik/8799/7)

/etc/systemd/system/cockpit.socket.d/listen.conf

```conf
[Socket]
ListenStream=
ListenStream=127.0.0.1:9090
ListenStream=172.17.0.1:9090
FreeBind=yes
```

/etc/cockpit/cockpit.conf

```conf
[WebService]
Origins = http://cockpit.notakrista.com ws://cockpit.notakrista.com https://cockpit.notakrista.com wss://cockpit.notakrista.com
ProtocolHeader = X-Forwarded-Proto
AllowUnencrypted=true
```

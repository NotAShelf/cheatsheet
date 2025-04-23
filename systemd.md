# Systemd Cheatsheet

Useful commands to interact with Systemd from your terminal

## List Units

```bash
systemctl --user list-units
```

## List Targets

```bash
systemctl --user --type=target
```

## Start a Service

```bash
systemctl start --user <name>.service
```

## Inspect System Service Journal

```bash
journalctl -xeu <name>.service
```

### Inspect Userspace Service Journal

```bash
journalctl --user -xeu <name>.service
```

## List Active Systemd Timers

```bash
systemctl list-timers --all
```

## Inspect Timer

```bash
systemctl status  <name>.timer
```

### Inspect Userspace Timer

```bash
systemctl status --user  <name>.timer
```

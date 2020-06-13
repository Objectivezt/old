`Error: ENOSPC: System limit for number of file watchers reached, watch`

```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p

sudo sysctl --system
```

```
gitlab-ctl
```

# redisinsight-web-ui
a docker image to run redisinsight with web interface

**to deploy on a linux/windows: **
download docker image redisinsight.tar from
https://drive.google.com/drive/folders/1LNpvCJ5fa8HvaaUtBj5ub-QbNL7XnZzL?usp=sharing

install docker (on linux via yum, on windows via docker desktop) and run (via bash/cmd):
```bash
docker load --input (path)/redisinsight.tar
docker run -d --name redisinsight -p 5540:5540 -v (your-disk-here):/data redis/redisinsight:latest
```

check if running and check logs for problems:
```bash
docker ps
docker logs redisinsight
```

you can then accsess the webui from:
http://(ip-of-server-running-docker):5540

if docker stop or shows permission error, disable selinux on server nad give 777 to data dir

for automatic start: 
```bash
systemctl enable podman
vi /usr/lib/systemd/system/podman.service
after ExecStart add:
ExecStartPost=/usr/bin/podman start redisinsight
```

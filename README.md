# redisinsight-web-ui
a docker image to run redisinsight with web interface

**to deploy on a linux/windows: **
download docker image redisinsight.tar from
https://drive.google.com/drive/folders/1LNpvCJ5fa8HvaaUtBj5ub-QbNL7XnZzL?usp=sharing

install docker (on linux via yum, on windows via docker desktop) and run (via bash/cmd):
```bash
docker load --input <path>/redisinsight.tar
docker run -d --name redisinsight -p 5540:5540 -v /<your-disk-here/>:/data redis/redisinsight:latest
```

you can then accsess the webui from:
http://<ip-of-server-running-docker>:5540

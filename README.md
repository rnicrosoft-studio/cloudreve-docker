# cloudreve-docker
Dockerfile for Cloudreve V3. A trial to use `Github Action`.

Inspired by [Cloudreve](https://github.com/cloudreve/Cloudreve/blob/master/Dockerfile) and [xavier-niu/cloudreve-docker](https://github.com/xavier-niu/cloudreve-docker)

## Run
```
docker run -d \
  --name cloudreve \
  -e TZ="Asia/Shanghai" \ # optional
  -p 5212:5212 \ 
  --restart=unless-stopped \ # optional
  -v <PATH TO UPLOADS>:/cloudreve/uploads \
  -v <PATH TO conf.ini>:/cloudreve/conf.ini \
  -v <PATH TO cloudreve.db>:/cloudreve/cloudreve.db \
  -v <PATH TO avatar>:/cloudreve/avatar \
  rnicrosoft/cloudreve
```

where
```
<PATH TO UPLOADS>: for upload files
<PATH TO conf.ini>: configuration file (not directory)
<PATH TO cloudreve.db>: database file (not directory)
<PATH TO avatar>: for avatar files
```

## Notes

Default timezone is `Asia/Shanghai`.
  
After the docker first run, use `docker logs -f cloudreve` to get the generated initial password.

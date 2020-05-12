dainli/puppeteer-linux

# 本地使用

1. 拉取镜像

```shell
docker pull dainli/puppeteer-linux
```

2. 切换到需要运行的目录

```shell
cd /path/project
```

3. 执行

```shell
docker run --cap-add=SYS_ADMIN -v `pwd`:`pwd` -w `pwd` -it dainli/puppeteer-linux /bin/bash -c "pwd && ls -ll && npm run build"
```

# 说明

## --no-sandbox 问题

1. 通过设置 --no-sandbox 运行

```js
const browser = await puppeteer.launch({
  args: ["--no-sandbox", "--disable-setuid-sandbox"],
});
```

2. 添加 --cap-add=SYS_ADMIN

# 参考

- [Dockerfile.linux](https://github.com/puppeteer/puppeteer/blob/master/.ci/node12/Dockerfile.linux)
- [No usable sandbox error when using --no-sandbox](https://github.com/puppeteer/puppeteer/issues/3451)

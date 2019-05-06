# PyOne

[PyOne](https://github.com/abbeyokgo/PyOne)项目的docker镜像

Dockerfile根据[TimeBye/docker-pyone](https://github.com/TimeBye/docker-pyone/blob/master/Dockerfile.alpine)修改而来

- ## 使用方法:

1. 从打包好的镜像运行:
```

mkdir pyone  && cd pyone

wget -O docker-compose.yaml https://github.com/9527tech/docker/raw/master/pyone/docker-compose.yaml

docker-compose up -d
```

2. 自行构建镜像运行:
```
git clone https://github.com/9527tech/docker.git

cd docker/pyone

docker build -t 9527tech/pyone .

docker-compose up -d
```

### P.S. pyone默认密码为:PyOne, 请及时修改密码

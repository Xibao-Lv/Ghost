## 打包部署(第一次)

### 部署Ghost

```
ghost_server="git@github.com:Xibao-Lv/Ghost.git"
ghost_tmp_dir="/tmp/Ghost"

if [ ! -d $ghost_tmp_dir ] then
    echo ">>> Clone Ghost from ${ghost_server}"
    git clone $ghost_server $ghost_tmp_dir
fi

cd $ghost_tmp_dir

git submodule update --init

echo ">>> npm install ..."
npm install

echo ">>> Building Ghost ..."
rm -rf .build/build/*
rm -rf .dist/build/*
grunt release

cd .dist/release
unzip Ghost-0.7.3.zip   ${DEPLOY_DIR}

```


https://gist.github.com/ErisDS/6f32e9b75d08a1c81f9b


### 部署Theme

https://gist.github.com/ErisDS/1866c7a1914c93a31a6c



## 更新部署(后续更新部署)


http://support.ghost.org/how-to-upgrade/

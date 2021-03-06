# docker-machine hypercore

## Dependency

- libmachine rpc driver plugin platform on [@nathanleclaire/machine](https://github.com/nathanleclaire/machine)
- xhyve cli written js by @maxogden [@maxogden/linux](https://github.com/maxogden/linux)
- *NOT PUBLISH* hypercore-boot2docker by zchee

## Install

```bash
# @nathanleclaire developpnig libmachine-rpc branch
go get github.com/nathanleclaire/machine
# Checkout branch
git checkout nathanleclaire/libmachine_rpc_plugins
# Make libmachine rpc include docker-machine_darwin-amd64 binary
cd script/build
# go get this repo
go get -d github.com/zchee/docker-machine-hypercore
# Intalll binary from /usr/local/bin/docker-machine-hypercore
make install
# Install hypercore(linux)
npm install linux -g
# Check docker-machine-hypercore driver server
docker-machine-hypercore
# Create hypercore(linux) vm use xhyve. driver server is auto execute in main docker-machine binary.
./docker-machine_darwin-amd64 create --driver hypercore hypercore

# ! Stop ! Now, It's finished commit code until here.

# Yourself run ssh command use sudo(./linux/id_rsa permission issue)
# IP address is you would have been seen on terminal log.
sudo /usr/local/bin/ssh -i ./linux/id_rsa -p 22 tc@192.168.**.**
```
Done. Possible ssh login TinyCore Linux.

## Future plan
- I came up to look at the source of hypercore. I’ve always wanted to try it.
- It corresponds to boot2docker and fix any issue when if I feel like it.


## Special Thanks

- [@maxogden](https://github.com/maxogden) wrote a xhyve control cli tool written js [linux](https://github.com/maxogden/linux)
- [@nathanleclaire](https://github.com/nathanleclaire) wrote a libmachine rpc plugin backend in the [docker/machine](https://github.com/nathanleclaire/machine).

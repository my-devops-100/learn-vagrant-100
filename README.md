# Vagrant by HashiCorp

|本期版本| 上期版本
|:---:|:---:
`Sun Jul 21 11:43:32 CST 2024` | -

## Install

### macOS

`Ventura`、`Monterey`

```bash
brew install vagrant
```

### Ubuntu

`22.04`

```bash
name=/etc/apt/sources.list.d/hashicorp.list
keyrings=/usr/share/keyrings/hashicorp-archive-keyring.gpg

sudo apt-get update && sudo apt-get install -y lsb-release wget

wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor --yes --output ${keyrings}
echo "deb [signed-by=${keyrings}] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee ${name}
sudo apt update && sudo apt install -y vagrant
```

```bash
sudo rm -f ${name}
```

## provision 

> `cloud-init`: [`https://github.com/hashicorp/vagrant/issues/5571#issuecomment-120430700`](https://github.com/hashicorp/vagrant/issues/5571#issuecomment-120430700)

```bash
config.vm.provision "shell", inline: "sleep 60"
```


## Ref

* [https://www.vagrantup.com/](https://www.vagrantup.com/)
* [Vagrant Cookbook - Second Edition](https://leanpub.com/vagrantcookbook) 、[Vagrant Cookbook - First Edition](https://1lib.us/book/2610987/b56779?id=2610987&secret=b56779&dsource=recommend)
* [熟练使用vagrant](https://www.junmajinlong.com/virtual/index/#vagrant)
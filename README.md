# CrowsEnv

Develop Enviroment of Nanozuki Crows. Managed by ansible.

## before to use

Before use these playbooks, should install ansible and fish.

### arch

```bash
sudo pacman -S ansible fish
chsh -s /bin/fish
```

### osx

First, Install [homebrew](https://brew.sh/), and:

```bash
brew install fish ansible
echo '/usr/local/bin/fish' | sudo tee -a /etc/shells
chsh -s /usr/local/bin/fish
```

### ansible

```bash
ansible-galaxy install -r requirements.yml
```

## bootstrap

put configure files to `$HOME/.config/CrowsEnv`, the structure of config like this:

```bash
├── git
│   ├── config_local
│   └── config_work
├── gpgkeys
│   ├── crows_pub.gpg
│   ├── crows_sec.gpg
│   ├── work_pub.gpg
│   └── work_sec.gpg
└── sshkeys
    ├── config
    ├── id_ed25519
    ├── id_ed25519.pub
    ├── id_work
    └── id_work.pub
```

and then:

```bash
curl -L https://raw.githubusercontent.com/nanozuki/CrowsEnv/master/crows-env.sh | bash -s bootstrap
```

## upgrade

modify config files or do git operator in $HOME/.data/CrowsEnv, and: 

```bash
crows-env upgrade
```

## update

update enviroment:

```bash
crows-env update
```

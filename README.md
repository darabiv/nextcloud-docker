## Step 1 - SSH into the server
```commandline
ssh youusername@yourhostip
```

## Step 2 - Install docker
Run these commands in terminal:
```commandline
sudo apt-get update
```

```commandline
sudo apt-get install ca-certificates curl
```

```commandline
sudo install -m 0755 -d /etc/apt/keyrings
```

```commandline
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
```

```commandline
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

```commandline
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```commandline
sudo apt-get update
```

```commandline
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Now the docker is installed. To make sure, check the version:
```commandline
docker --version
```

## Step 3 - Pull this repo
```commandline
 git@github.com:darabiv/nextcloud-docker.git
```

## Step 4 - Change db.env
CD into the cloned directory and change db passwords and user as your need
```commandline
cd nextcloud-docker
```
```commandline
vim db.env
```

## Step 5 - Create Bash Aliases
```bash
vim ~/.bash_aliases
```

Add these lines and save:
```
alias dcnext='docker compose -f docker-compose.nextcloud.yml'
```

Activate
```bash
source ~/.bashrc
```

## Step 6 - Bring up
Run:
```commandline
dcnext up -d
```

## Step 7 - Confirm that the containers are running
To ensure that the containers are up and running as expected, execute the following command:

```commandline
docker ps
```

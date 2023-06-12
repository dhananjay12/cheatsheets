# Colima

Alternative to docker desktop - [Github](https://github.com/abiosoft/colima)

```
brew install colima
```

To change default cpu/ram usage
```
colima start --mount $HOME:w --cpu 6 --memory 12
```
To start it with K8s (kubectl is required)
```
colima start --mount $HOME:w --kubernetes --cpu 6 --memory 12
```
Whatever you use, it will remember the previous configuration. Could setup in bash profile
```
alias k-start="colima start --mount $HOME:w --kubernetes --cpu 6 --memory 12"
alias k-stop="colima stop"
alias d-start="colima start --mount $HOME:w --cpu 6 --memory 12"
alias d-stop="colima stop"
```


If you are upgrading or your setup is behaving weiredly, it is required to start afresh by deleting existing instance.
```
colima delete # delete existing instance (Delete ~/.colima if there are any issues)
colima start
```

Some tools reply of `DOCKER_HOST` env variable to work. Its better to have it in zshenv/zshrc or bash_profile

```
echo 'export TESTCONTAINERS_RYUK_DISABLED=true' >> ~/.zshenv
echo 'export DOCKER_HOST=unix://$HOME/.colima/docker.sock' >> ~/.zshenv
source ~/.zshenv
```

# K9s

K9s provides a terminal UI to interact with your Kubernetes clusters - [Github](https://github.com/derailed/k9s)

```
brew install k9s
```

Start by typing `k9s` in terminal.

Make sure your K8s context or cluster is pointing to correct cluster.

```
kubectl config get-contexts                          # display list of contexts. Check *
kubectl config use-context my-cluster-name           # set the default context to my-cluster-name

kubectl config set-cluster my-cluster-name           # set a cluster entry in the kubeconfig
```

# Lazydocker

A simple terminal UI for both docker and docker-compose - [Github](https://github.com/jesseduffield/lazydocker)

```
brew install lazydocker
```

Call `lazydocker` in your terminal. You can have an alias in zshenv/zshrc or bash_profile
```
echo "alias lzd='lazydocker'" >> ~/.zshenv
source ~/.zshenv
```

[Keybindings_en](https://github.com/jesseduffield/lazydocker/blob/master/docs/keybindings/Keybindings_en.md)

Note - If you have colima as docker, you need to have a DOCKER_HOST env variable poiting to that.

Copying logs directly is not possible from the default UI. To do the same follow following steps

* Press m to attach to container

* Copy logs

* Return to lazydocker by pressing ctrl-c

# Json log Viewer

View Json logs locally - [Github](https://github.com/gistia/json-log-viewer)

```
npm install --global json-log-viewer
```

Usage

```
jv application.log
```
Select the line to expand and see starcktrace if any

`f` filter 

`/` search and `n` search again

`Esc` to go back

`q` to quit


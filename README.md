# tmux-ubuntu

# upgrade new version
```
# Get new version from ubuntu
# At root of repository
dget -x http://archive.ubuntu.com/ubuntu/pool/main/t/tmux/tmux_2.6-3.dsc
rm -rf tmux && mv tmux-2.6 tmux
git add tmux
git commit -m "Upgrade tmux to 2.6"
TAG=2.6-3
git tag $TAG
git push --tags
git archive --prefix=tmux-$TAG/ -o tmux-$TAG.tar.gz refs/tags/${TAG}:tmux/
sha256sum -b tmux-$TAG.tar.gz > tmux-$TAG.tar.gz.sha256
```

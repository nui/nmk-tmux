# nmk-tmux
Tmux used in nmkpkg

# Compile from source
```sh
TAG=2.7
pushd -q <TMUX DIR>
git archive --prefix=tmux-$TAG/ HEAD | tar -x -C ~/foss/nmk-tmux
popd
rm -rf tmux && mv tmux-$TAG tmux

git archive --prefix=tmux-$TAG/ -o tmux-$TAG.tar HEAD:tmux/
gzip tmux-$TAG.tar
sha256sum -b tmux-$TAG.tar.gz > tmux-$TAG.tar.gz.sha256
```

# upgrade new version from debian
2.9 is built from this method

```sh
# Get new version from ubuntu
# At root of repository
dget -x http://archive.ubuntu.com/ubuntu/pool/main/t/tmux/tmux_2.6-3.dsc
rm -rf tmux && mv tmux-2.6 tmux
git add tmux
git commit -m "Upgrade tmux to 2.6"
TAG=2.6-3
git tag $TAG
git push --tags
git archive --prefix=tmux-$TAG/ -o tmux-$TAG.tar refs/tags/${TAG}:tmux/
gzip tmux-$TAG.tar
sha256sum -b tmux-$TAG.tar.gz > tmux-$TAG.tar.gz.sha256
```

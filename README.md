# nmk-tmux
Tmux used in nmkpkg

# upgrade new version from debian
3.3a is built from this method

```sh
# Get new version from ubuntu
# At root of repository
dget -x http://deb.debian.org/debian/pool/main/t/tmux/tmux_3.4-3.dsc
rm -rf tmux && mv tmux-3.4 tmux
git add tmux
git commit -m "Upgrade to tmux 3.4-3"
TAG=3.4-3
git tag $TAG
git push && git push --tags
git archive --prefix=tmux-$TAG/ -o tmux-$TAG.tar refs/tags/${TAG}:tmux/
gzip tmux-$TAG.tar
sha256sum -b tmux-$TAG.tar.gz > tmux-$TAG.tar.gz.sha256
```

## split-and-cat
split and re-assemble large file in order to store them on Github

## split and cat (Strong Recommended)
so can be stored directly on Github

### split .tar.gz into 20M one slice
```bash
split -b 20m jdk-8u161-linux-x64.tar.gz jdk-8u161-linux-x64
> ls packages/jdk-splits/
jdk-8u161-linux-x64aa  jdk-8u161-linux-x64ac  jdk-8u161-linux-x64ae  jdk-8u161-linux-x64ag  jdk-8u161-linux-x64ai
jdk-8u161-linux-x64ab  jdk-8u161-linux-x64ad  jdk-8u161-linux-x64af  jdk-8u161-linux-x64ah  jdk-8u161-linux-x64aj
```
### re-assemble slice into one .tar.gz
```bash
cat jdk-8u161-linux-x64a* > jdk-8u161-linux-x64.tar.gz
```

## Deprecated git-lfs now
git-lfs was free only for 1G bandwidth(yes, you did not misread), so mean

so I decided to quit using it though I had just tried it.

### git-lfs
```bash
git lfs - large file storage
brew install git-lfs
```
```bash
git lfs install
git lfs track "*.tar.gz"

git add packages/
git add .gitattributes

> cat .gitattributes
*.tar.gz filter=lfs diff=lfs merge=lfs -text

git lfs ls-files
ad78d0908a * packages/apache-tomcat-8.5.27.tar.gz
6dbc56a0e3 * packages/jdk-8u161-linux-x64.tar.gz
```

# Karaoke Mugen App Flathub package

### Update generated-sources.json
```
git clone -b yarn2 https://github.com/Dragicafit/flatpak-builder-tools/
cd flatpak-builder-tools/node

python3 -m venv venv
source venv/bin/activate
pip install .

cd ../..

flatpak-node-generator yarn -r yarn.lock -R kmfrontend/yarn.lock -R yarn.lock 
```

### Build
`flatpak-builder --force-clean --user --install-deps-from=flathub --repo=repo --install builddir moe.karaokes.mugen.yml` 


### Troubleshoot
If on bigger drives the build fails because of apparently low percentage of disk space, ignore it with the flag
`ostree --repo=repo config set core.min-free-space-size 1GB`
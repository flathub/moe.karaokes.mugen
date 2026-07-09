# Karaoke Mugen App Flathub package

## Update generated-sources.json
Updating the `generated-sources.json` file is normally necessary when upgrading karaokemugen-app to a newer release.

Install a patched version of flatpak-node-generator in a python venv:

```
git clone -b yarn2 https://github.com/Dragicafit/flatpak-builder-tools/
cd flatpak-builder-tools/node

python3 -m venv venv
source venv/bin/activate
pip install .
```

Then in the same activated venv, cd into the karaokemugen-app project folder and execute flatpak-node-generator:

```
flatpak-node-generator yarn -r yarn.lock -R kmfrontend/yarn.lock -R yarn.lock
```

Copy the freshly generated `generated-sources.json` from the karaokemugen-app folder into this repository (overwriting the existing file)

## Build
`flatpak-builder --force-clean --user --install-deps-from=flathub --repo=repo --install builddir moe.karaokes.mugen.yml` 

## Troubleshoot
If on bigger drives the build fails because of apparently low percentage of disk space, ignore it with the flag
`ostree --repo=repo config set core.min-free-space-size 1GB`
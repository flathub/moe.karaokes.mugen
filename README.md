# Karaoke Mugen App Flathub package

### Build
`flatpak-builder --force-clean --user --install-deps-from=flathub --repo=repo --install builddir moe.karaokes.mugen.yml` 


### Troubleshoot
If on bigger drives the build fails because of apparently low percentage of disk space, ignore it with the flag
`ostree --repo=repo config set core.min-free-space-size 1GB`
## General

Building AppImage packages from existing software projects using Github workflow.

References:
- <https://docs.appimage.org/packaging-guide/converting-binary-packages/pkg2appimage.html>
- <https://appimage-builder.readthedocs.io/en/latest/index.html>
- <https://appimage-builder.readthedocs.io/en/latest/hosted-services/github-actions.html> 

Tested so far on:

- Rocky Linux 8.6 (using Docker)
- Fedora 34 (using Podman user-mode)

## Building appimage recipes

```
$ docker run -it --rm -v $PWD/recipes:/recipes:ro -v $PWD/output:/output --workdir /output/  appimagecrafters/appimage-builder appimage-builder --recipe /recipes/test.yml --skip-test
```

## Building pkg2appimage recipes

```
$ docker run -it -v $PWD/buildout:/buildout:z -v $PWD/recipes:/recipes:ro ghcr.io/akisys/pkg2appimage-containerized /recipes/NoMachine-Enterprise-Client-7.10_x86_64
```

Creates the recipe according to definition in the `buildout` folder.

## License

This project is licensed under MIT and is made available as-is.  
Licenses of the used components are unchanged and belong to their respective license holders.

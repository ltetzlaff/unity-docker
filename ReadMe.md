# unity-docker

Based on [grableroux/unity3d](https://gitlab.com/gableroux/unity3d).

Linux Unity3d builds are taken from [Unity on Linux: Release Notes and Known Issues](https://forum.unity3d.com/threads/unity-on-linux-release-notes-and-known-issues.350256/)

## Usage

### Build the image

```bash
docker build -t <reg>/<name>:<tag> .
```

### Run the image

```bash
docker run -it --rm \
  -v "$(pwd):/root/project" \
  gableroux/unity3d:latest \
  xvfb-run --auto-servernum --server-args='-screen 0 640x480x24' \
  /opt/Unity/Editor/Unity -projectPath /root/project
```

### Gitlab-CI

This docker image is intended to be used with [gitlab-ci](https://about.gitlab.com/features/gitlab-ci-cd/) (but may work with other CIs). An example project using unity3d in a docker image can be found at **[gableroux/unity3d-gitlab-ci-example](https://gitlab.com/gableroux/unity3d-gitlab-ci-example)**. Have a look to the `.gitlab-ci.yml`.

## License

[MIT](LICENSE.md)


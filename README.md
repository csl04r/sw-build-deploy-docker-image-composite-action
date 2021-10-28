
## Build & Deploy Docker Image to Artifactory

`Required` parameters:
- `artifactory_registry:` -> registry url
- `artifactory_username:` -> username
- `artifactory_api_key:`  -> password

`Optional` parameters:
- `dockerfile_path:`   -> location of dockerfile(s)
- `image_name:`        -> specify image name to deploy
- `docker_build_args:` -> any build arguments

Usage:
```
jobs:
  build-deploy:
    runs-on: sw-rancher-runnerset
    steps:
      - uses: actions/checkout@v2
      
      - uses: sherwin-williams-co/sw-build-deploy-docker-image-action@main
        with:
          artifactory_registry: ${{ secrets.ARTIFACTORY_REGISTRY }}
          artifactory_username: ${{ secrets.ARTIFACTORY_USERNAME }}
          artifactory_api_key: ${{ secrets.ARTIFACTORY_API_KEY }}
          dockerfile_path: # optional docker/Dockerfile
          image_name: # optional image_name/image
          docker_build_args: |
            # optional args1=1
            # optional args2=2
```

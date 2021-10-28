
# Composite Action  
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
          dockerfile_path: docker/Dockerfile
          image_name: TestDeleteme/TestDeleteme
          docker_build_args: |
            args1=1
            args2=2
```

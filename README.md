
## Build & Deploy Docker Image to Artifactory

### Parameters: 
Name | Type |        | Default |
---  | ---  | ---------- | ------- |
`artifactory_registry`| String | Required
`artifactory_username` | String | Required
`artifactory_api_key` | String | Required
`dockerfile_path` | String | *Optional*  | `Dockerfile`
`image_name`      | String | *Optional*  | `${{ github.repository }}`
`docker_build_args` | String | *Optional*


Usage:
```yaml
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
          # optional
          dockerfile_path: docker/Dockerfile
          image_name: image_name/image
          docker_build_args: |
            args1=1
            args2=2
```

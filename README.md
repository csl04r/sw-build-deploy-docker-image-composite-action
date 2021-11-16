
## Build & Deploy Docker Image to Registry

### Parameters: 
Name | Type |        | Default |
---  | ---  | ---------- | ------- |
`image_registry`| Secret | Required*
`image_registry_username` | Secret | Required*
`image_registry_api_key` | Secret | Required*
`github_token` | String | *Optional* | `${{ github.TOKEN }}`
`dockerfile_path` | Path | *Optional*  | `Dockerfile`
`image_name`      | String | *Optional*  | `${{ github.REPOSITORY }}`
`buildcontext` | Path | *Optional* | `.`
`docker_build_args` | String | *Optional*

Usage:
```yaml
jobs:
  build-deploy:
    runs-on: sw-ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - uses: sherwin-williams-co/sw-build-deploy-docker-image-composite-action@main
        with:
          image_registry: ${{ secrets.ARTIFACTORY_REGISTRY }}
          image_registry_username: ${{ secrets.ARTIFACTORY_USERNAME }}
          image_registry_api_key: ${{ secrets.ARTIFACTORY_API_KEY }}
          # Optional
          # github_token: ${{ github.TOKEN }}
          # dockerfile_path: docker/Dockerfile
          # image_name: image_name/image
          # buildcontext: .
          # docker_build_args: |
            # args1=1
            # args2=2
```


## Build & Deploy Docker Image to Artifactory

### Parameters: 
Name | Type |        | Default |
---  | ---  | ---------- | ------- |
`artifactory_registry`| Secret | Required*
`artifactory_username` | Secret | Required*
`artifactory_api_key` | Secret | Required*
`github_token` | String | *Optional* | `${{ GITHUB.TOKEN }}`
`dockerfile_path` | Path | *Optional*  | `Dockerfile`
`image_name`      | String | *Optional*  | `${{ GITHUB.REPOSITORY }}`
`buildcontext` | Path | *Optional* | `.`
`docker_build_args` | String | *Optional*

Usage:
```yaml
jobs:
  build-deploy:
    runs-on: sw-ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - uses: sherwin-williams-co/sw-build-deploy-docker-image-action@main
        with:
          artifactory_registry: ${{ secrets.ARTIFACTORY_REGISTRY }}
          artifactory_username: ${{ secrets.ARTIFACTORY_USERNAME }}
          artifactory_api_key: ${{ secrets.ARTIFACTORY_API_KEY }}
          # Optional
          # github_token: ${{ GITHUB.TOKEN }}
          # dockerfile_path: docker/Dockerfile
          # image_name: image_name/image
          # buildcontext: .
          # docker_build_args: |
            # args1=1
            # args2=2
```

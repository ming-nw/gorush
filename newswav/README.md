## Gorush (NW)
If a new version of Gorush is available, it's recommended to pull the latest Docker image and update our deployment. Here's how to check for and update the latest version:

```bash
# Check for the latest Gorush version:
docker pull appleboy/gorush:latest

# If the version has been updated (e.g., to 1.18), push the new image to our GCP Artifact Registry:
docker pull appleboy/gorush:1.18
docker tag appleboy/gorush:latest asia-southeast1-docker.pkg.dev/bustling-sunset-220007/newswav-gorush/newswav-gorush:nw-v1.18
docker push asia-southeast1-docker.pkg.dev/bustling-sunset-220007/newswav-gorush/newswav-gorush:nw-v1.18
```

Update the Gorush deployment to use the new version by modifying the Helm values file (gorush-values.yaml) to reflect the new image tag and then run the upgrade command again.

## GORUSH CONFIGMAP
`helm upgrade -i -n gorush -f gorush-cm.yaml gorush-config oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2`

## GORUSH SECRET
`helm upgrade -i -n gorush -f gorush-secret.yaml gorush-gcpsm oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2`

# REDIS-GORUSH
`helm upgrade -i -n gorush -f redis-values.yaml redis bitnami/redis --history-max 2`

# GORUSH - PN_URL
`helm upgrade -i -n gorush -f gorush-values.yaml gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2`

# HMS-GORUSH - HMS_PN_URL
`helm upgrade -i -n gorush -f hms-gorush-values.yaml hms-gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2`

# INSTANT-GORUSH -INSTANT_PN_URL
`helm upgrade -i -n gorush -f instant-gorush-values.yaml instant-gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2`

# MISC-GORUSH - COMMENT_GORUSH_HOST
`helm upgrade -i -n gorush -f misc-gorush-values.yaml misc-gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2`
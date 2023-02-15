## GORUSH CONFIGMAP

helm upgrade -i -n gorush -f gorush-cm.yaml gorush-config oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2

# REDIS-GORUSH 

helm upgrade -i -n gorush -f redis-values.yaml redis bitnami/redis --history-max 2

# GORUSH - PN_URL

helm upgrade -i -n gorush -f gorush-values.yaml gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2

# HMS-GORUSH - HMS_PN_URL

helm upgrade -i -n gorush -f hms-gorush-values.yaml hms-gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2

# INSTANT-GORUSH -INSTANT_PN_URL

helm upgrade -i -n gorush -f instant-gorush-values.yaml instant-gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2

# MISC-GORUSH - COMMENT_GORUSH_HOST

helm upgrade -i -n gorush -f misc-gorush-values.yaml misc-gorush oci://asia-southeast1-docker.pkg.dev/nw-development-329802/newswav-helm/newswav-app --history-max 2
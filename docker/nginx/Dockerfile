# Pulls a slim image from Docker Hub, maintained by MySQL.
# This uses alpine, which is a distribution of choice to keep the docker images size small.
# The environment uses slightly different set of commands to manage packages.
# Tag is specific as much as possible to reduce unexpected changes.

# Current Stable (June 2020)
FROM nginx:1.18.0-alpine

# Author of this image.
LABEL maintainer="andy@spacemeld.com"

CMD ["nginx", "-g", "daemon off;"]

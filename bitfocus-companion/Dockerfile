ARG BUILD_ARCH=aarch64

# Select the correct image based on the architecture linux/arm64=aarch64_image linux/amd64=amd64_image
FROM ghcr.io/bitfocus/companion/companion:3.5.3-7770-stable-df70e20b@sha256:ff126d7fa635ae9f64568d522432f7665dc8c846f067302b39ae55eb513472a5 AS aarch64_image
FROM ghcr.io/bitfocus/companion/companion:3.5.3-7770-stable-df70e20b@sha256:813dfd0f40a570f2fd1a4e390edd9e19fa21c790c3b2068af54213f1e2c2f2cf AS amd64_image


# The actual image used
FROM ${BUILD_ARCH}_image

USER root

# Copy the startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Change the entry point
ENTRYPOINT ["/run_companion.sh"]

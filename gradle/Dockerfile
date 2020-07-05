# Simple Dockerfile adding Maven and GraalVM Native Image compiler to the standard
# https://hub.docker.com/r/oracle/graalvm-ce image
FROM oracle/graalvm-ce:20.1.0-java11

LABEL maintainer="Dominique Lopes (https://github.com/d-lopes)"

# For SDKMAN to work we need unzip & zip
RUN yum install -y unzip zip

RUN \
    # Install SDKMAN
    curl -s "https://get.sdkman.io" | bash; \
    source "$HOME/.sdkman/bin/sdkman-init.sh"; \
    sdk install gradle; \
    # Install GraalVM Native Image
    gu install native-image;

RUN source "$HOME/.sdkman/bin/sdkman-init.sh" && gradle --version

RUN native-image --version

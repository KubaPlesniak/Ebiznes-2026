FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive
ENV SDKMAN_DIR=/root/.sdkman

SHELL ["/bin/bash", "-c"]

RUN apt-get update && \
    apt-get install -y openjdk-8-jdk curl zip unzip ca-certificates && \
    rm -rf /var/lib/apt/lists/*

RUN curl -s "https://get.sdkman.io" | bash && \
    source "$SDKMAN_DIR/bin/sdkman-init.sh" && \
    sdk install kotlin && \
    ln -s "$SDKMAN_DIR/candidates/kotlin/current/bin/kotlinc" /usr/local/bin/kotlinc && \
    ln -s "$SDKMAN_DIR/candidates/kotlin/current/bin/kotlin" /usr/local/bin/kotlin

CMD bash -lc "java -version && kotlinc -version"
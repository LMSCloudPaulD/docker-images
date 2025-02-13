FROM debian:bookworm-slim

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    devscripts \
    vim \
    && rm -rf /var/lib/apt/lists/*

# These will be provided at runtime
ENV USER_ID=1000
ENV USERNAME=developer
ENV DEBEMAIL=""
ENV DEBFULLNAME=""
ENV EDITOR="vim"

# Create a non-root user with provided UID
RUN useradd -u ${USER_ID} -m -s /bin/bash ${USERNAME}

WORKDIR /workspace

# Create and set permissions for workspace
RUN mkdir -p /workspace && chown ${USERNAME}:${USERNAME} /workspace

# Switch to the non-root user
USER ${USERNAME}

# Keep container running for interactive use
ENTRYPOINT ["tail", "-f", "/dev/null"]

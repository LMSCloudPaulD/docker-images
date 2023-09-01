FROM debian:bookworm-slim

# Install necessary packages
RUN apt-get update && \
  apt-get install -y --no-install-recommends \
  build-essential \
  ca-certificates \
  cmake \
  debhelper \
  devscripts \
  fakeroot \
  git \
  git-buildpackage \
  gnupg \
  lintian \
  tree \
  vim

# Create a non-root user with UID 1001
RUN useradd -ms /bin/bash builder -u 1001

# Set the working directory
WORKDIR /home/builder

# Set the user PATH (optional, only if you need to add local/bin for this user)
ENV PATH="/home/builder/.local/bin:${PATH}"

# Use user builder
USER builder

# Keep the container running
CMD ["tail", "-f", "/dev/null"]


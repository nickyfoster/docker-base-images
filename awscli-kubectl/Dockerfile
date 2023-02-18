FROM debian:stable-slim

# Install AWS CLI
RUN apt update && apt install -y \
        curl \
        unzip \
        ca-certificates \
    && curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && /aws/install \
    && rm -rf /var/lib/apt/lists/*


# Install kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" \
    && install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

# RUN aws --version
# RUN kubectl version
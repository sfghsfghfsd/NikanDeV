FROM kalilinux/kali-rolling

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt install -y \
    kali-linux-headless \
    openvpn \
    nmap \
    netcat-traditional \
    curl \
    wget \
    git \
    jq

# Go-based tools
RUN curl -LO https://go.dev/dl/go1.21.1.linux-amd64.tar.gz && \
    tar -C /usr/local -xzf go1.21.1.linux-amd64.tar.gz && \
    rm go1.21.1.linux-amd64.tar.gz

ENV PATH="/usr/local/go/bin:$PATH"

RUN go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest && \
    mv /root/go/bin/nuclei /usr/local/bin/

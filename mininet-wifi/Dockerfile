FROM ramonfontes/mininet-wifi

ADD dashc /root/dashc
ADD topology.py /root/.

USER root
WORKDIR /root

COPY ENTRYPOINT.sh /

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    iproute2 \
    iputils-ping \
    net-tools \
    tcpdump \
    vim \
    x11-xserver-utils \
    openssh-server \
    xauth \
    wget \
    vlc \
    xterm \
    ffmpeg \
    libc6-i386 \
    p7zip \
    bzip2 \
 && rm -rf /var/lib/apt/lists/* \
 && echo AddressFamily inet >> /etc/ssh/sshd_config \
 && sed -i 's/prohibit-password/yes/' /etc/ssh/sshd_config \
 && sed -i 's/geteuid/getppid/' /usr/bin/vlc \
 && chmod +x /ENTRYPOINT.sh \
 && /etc/init.d/ssh restart

EXPOSE 6633 6653 6640

ENTRYPOINT ["/ENTRYPOINT.sh"]

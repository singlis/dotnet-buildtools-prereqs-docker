FROM arm32v7/ubuntu:16.04

# Install Helix Dependencies 

RUN apt-get update && \
    apt-get install -y \        
        gss-ntlmssp \
        iputils-ping \
        libcurl3 \
        libffi-dev \
        libgdiplus \        
        libicu-dev \        
        libssl-dev \
        libunwind8 \        
        libunwind-dev \        
        locales \
        locales-all \
        python-dev \
        python-pip \        
        tzdata \
        unzip \              
    && rm -rf /var/lib/apt/lists/* \
    \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8

ENV LANG en_US.utf8

RUN python -m pip install --upgrade pip==19.0.2 && \
    python -m pip install \ 
                  applicationinsights==0.11.7 \
                  certifi==2018.11.29 \
                  cryptography==2.5 \                  
                  docker==3.6.0 \
                  ndg-httpsclient==0.5.1  \
                  psutil==5.4.8 \
                  pyasn1==0.4.5 \
                  pyopenssl==18.0.0 \
                  requests==2.21.0 \
                  six==1.12.0 \
                  virtualenv==16.2.0

RUN adduser --disabled-password --gecos '' --uid 1001 --ingroup sudo helixbot && \
    chmod -R +x /root && \
    echo 'helixbot ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER helixbot
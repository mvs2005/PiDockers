FROM arm32v7/debian
RUN apt-get update \ 
 && apt install -y curl \
 && apt-get install -y  sudo \
 && apt-get install -y wget \
 && rm -rf /var/lib/apt/lists/*

RUN apt-get install -y debian-archive-keyring \
 && apt-get update \
 && apt-get install -y curl gnupg apt-transport-https \
 && curl -s https://packagecloud.io/install/repositories/headmelted/codebuilds/script.deb.sh | sudo bash \
 && curl -L https://code.headmelted.com/installers/apt.sh | sudo bash \
 && apt-get update \
 && apt-get install -y gconf-service libasound2 libatk1.0-0 libc6 \
 && apt-get install -y libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 \
 && apt-get install -y libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 \
 && apt-get install -y libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 \
 && apt-get install -y libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 \
 && apt-get install -y libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 \
 && apt-get install -y libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation \
 && apt-get install -y libappindicator1 libnss3 lsb-release xdg-utils wget \
 && apt-get update

RUN apt-get purge -y code-oss \
 && apt-get install -y code-oss=1.29.0-1539702286 \
 && apt-mark hold code-oss \
 && sed -i 's/BIG-REQUESTS/_IG-REQUESTS/' /usr/lib/arm-linux-gnueabihf/libxcb.so.1

# docker build -t vscode ~/Dockers/vscode
# x11docker vscode --clipboard

RUN adduser vs --disabled-password
USER vs
ENTRYPOINT ["/usr/share/code-oss/code-oss --disable-gpu"]
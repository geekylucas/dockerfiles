# To build:
# docker build -t geekylucas/1password-wine .
#
# To run:
# docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY -v $HOME/Dropbox/1Password.agilekeychain:/root/Dropbox/1Password.agilekeychain --net="host" --name 1password-wine geekylucas/1password-wine bash
#
# To operate:
# Use up arrow for handy commands
#
# To start after first run:
# docker start -i geekylucas/1password-wine

FROM jess/wine
MAINTAINER Lucas Chan <docker@lucaschan.com>

ADD https://d13itkw33a7sus.cloudfront.net/dist/1P/win4/1Password-4.6.0.598.exe /usr/src/1Password-4.6.0.598.exe

RUN echo "wine /root/.wine/drive_c/Program\ Files/1Password\ 4/Agile1pAgent.exe" > /root/.bash_history
RUN echo "wine /root/.wine/drive_c/Program\ Files/1Password\ 4/1Password.exe" >> /root/.bash_history
RUN echo "wine /usr/src/1Password-4.6.0.598.exe" >> /root/.bash_history

EXPOSE 6258

CMD [ "bash" ]

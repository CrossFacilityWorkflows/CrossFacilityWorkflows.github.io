FROM ubuntu:20.04
LABEL maintainer="Johannes Blaschke <jpblaschke@lbl.gov>"

# Base Ubuntu packages

ENV DEBIAN_FRONTEND noninteractive
ENV LANG C.UTF-8


RUN apt-get update && apt-get install -y \
      bash                               \
      fluxbox                            \
      git                                \
      net-tools                          \
      novnc                              \
      supervisor                         \
      x11vnc                             \
      xterm                              \
      xvfb                               \
      terminator

RUN ln -s /usr/share/novnc/vnc_auto.html /usr/share/novnc/index.html

# Setup demo environment variables
ENV LANG=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    LC_ALL=C.UTF-8 \
    DISPLAY=:0.0 \
    DISPLAY_WIDTH=1600 \
    DISPLAY_HEIGHT=968 \
    RUN_TERMINATOR=yes \
    RUN_FLUXBOX=yes

COPY . /srv
COPY novnc/passwd /root/.vnc/passwd

RUN mkdir -p /root/.fluxbox
RUN ln -s /srv/fluxbox/startup.sh /root/.fluxbox/startup
RUN cp /srv/fluxbox/init /root/.fluxbox/init

CMD ["/srv/entrypoint.sh"]
EXPOSE 8080
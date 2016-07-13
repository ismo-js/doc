FROM base/archlinux

MAINTAINER Te Standby <testandby@gmail.com>

LABEL
  io.k8s.didsplay-name="Doc"
  io.openshift.tags="doc"
  io.openshift.s2i.scripts-url="image:///app"

RUN
  pacman -S --noconfirm nodejs

COPY ["run", "assemble", "usage", "/app/"]

CMD ["/app/usage"]

FROM fedora:28
LABEL maintainer="Major Hayden <major@redhat.com>"
RUN echo "fastestmirror=true" >> /etc/dnf/dnf.conf
ADD dnf-transaction.txt /tmp/dnf-transaction.txt
RUN dnf -y install python2-pip && \
      dnf -y shell /tmp/dnf-transaction.txt && \
      dnf -y clean all && \
      rm -fv /tmp/dnf-transaction.txt
CMD ["/bin/bash", "-c"]

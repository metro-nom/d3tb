FROM mleist/py36slim:3.9.1

COPY requirements.txt /requirements.txt
COPY apk-requirements.txt /apk-requirements.txt
COPY build-requirements.txt /build-requirements.txt

RUN /entrypoint.sh -x \
  && curl -Lsf 'https://github.com/jgm/pandoc/releases/download/2.7.2/pandoc-2.7.2-1-amd64.deb'\
    | bsdtar xOf - data.tar.xz | xzcat\
    | tar xv --strip-components 2 -C /usr/local\
  && echo

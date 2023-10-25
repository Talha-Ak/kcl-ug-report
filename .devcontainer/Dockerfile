FROM registry.gitlab.com/islandoftex/images/texlive:latest-basic
ARG TEXLIVE_VERSION=2023

RUN apt-get update && apt-get install -y \
    # sharing ssh credentials
    openssh-client \
    # svg dep
    inkscape \
    # latexindent deps
    libyaml-tiny-perl libfile-homedir-perl libunicode-linebreak-perl liblog-log4perl-perl libtest-log-dispatch-perl

ENV PATH ${PATH}:/usr/local/texlive/${TEXLIVE_VERSION}/bin/x86_64-linux:/usr/local/texlive/${TEXLIVE_VERSION}/bin/aarch64-linux

RUN tlmgr install \
    # tooling
    latexmk chktex latexindent \
    # svg + deps
    svg koma-script trimspaces xcolor transparent pgf catchfile \
    datetime2 datetime2-english \
    glossaries \
    && texhash

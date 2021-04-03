BootStrap: docker
From: ubuntu:20.04

%labels
    Maintainer Osamu Ogasawara
        Version    v1.0


%setup
	cp *.sty /tmp/


%post
    echo "Hello from inside the container"
    apt-get -y update
    apt-get -y upgrade

    # Noninteractive install of tzdata
	# https://stackoverflow.com/questions/44331836/apt-get-install-tzdata-noninteractive
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends tzdata

    # Install platex, xelatex, etc.
	apt install -y texlive-science
	apt install -y texlive-lang-japanese
	apt install -y texlive-xetex
	apt install -y texlive-lang-cjk xdvik-ja evince
	apt install -y texlive-fonts-recommended texlive-fonts-extra

    # Copy additional style files
	cp /tmp/*.sty /usr/share/texmf/tex/latex
	mktexlsr

	# Install pandoc document converter.
	apt install -y pandoc
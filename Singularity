Bootstrap: docker
From: continuumio/miniconda3:4.5.4

%help
A Singularity image for chewBBACA v 2.0.12

%labels
Maintainer Kristy Horan
Build 1.0

%post
	echo "Setting up installation requirements"
	export PATH=/opt/conda/bin:$PATH
	python3 -m pip install --upgrade pip
	cd /opt/	
	echo "Installing chewBBACA."
	pip3 install chewbbaca==2.0.12
	pip3 install --upgrade numpy
	
	
	

%runscript
	echo "Welcome to a chewBBACA pipeline. May the force be with you"
	exec chewBBACA.py "$@"
%test

	/opt/conda/bin/chewBBACA.py -h	

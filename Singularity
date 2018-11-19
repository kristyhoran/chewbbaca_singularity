Bootstrap: docker
From: continuumio/miniconda3:4.5.4

%help
A Singularity image for chewBBACA v 2.0.16

%labels
Maintainer Kristy Horan
Build 1.1

%post
	export PATH=/opt/conda/bin:$PATH

	conda config --add channels conda-forge
	conda config --add channels defaults
	conda config --add channels r
	conda config --add channels bioconda

	conda install  snakemake=5.3.0

        echo "Setting up installation requirements"
        export PATH=/opt/conda/bin:$PATH
        python3 -m pip install --upgrade pip
        cd /opt/
        echo "Installing chewBBACA."
        pip3 install chewbbaca==2.0.16
        
        echo "Installing blastp"
        conda install blast
	echo "Installing prodigal"
	conda install prodigal

%environment
	export PYTHONNOUSERSITE=NO
        export PYTHONSITE=/opt/conda/lib/python3.6/site-packages

%runscript
        echo " A container for chewBBACA "
        chewBBACA.py "@"

%test

        /opt/conda/bin/chewBBACA.py -h



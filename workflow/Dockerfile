FROM condaforge/mambaforge:latest
LABEL io.github.snakemake.containerized="true"
LABEL io.github.snakemake.conda_env_hash="e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855"

## Dockerfile to build Docker image for this Snakemake workflow.

# Step 1: Install the essentials

RUN apt-get update &&\
    apt-get install -f -y &&\
    apt-get install build-essential -y &&\
    apt-get install git -y &&\
    apt-get install python3-pip

# Step 2: Retrieve conda environments

# Conda environment:
#   source: envs/salmon.yaml
#   prefix: /conda-envs/e7731bb49f40c7aec2d59fb33378cd57
#   name: salmon
#   channels:
#       - bioconda
#   dependencies:
#       - salmon

RUN conda install -c bioconda salmon

# Step 3: Install and test Snakemake

RUN conda install wheel &&\
    conda install snakemake

ENV PATH="~/.local:$PATH"

CMD ["Everything installed!"]
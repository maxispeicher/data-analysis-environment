FROM micwittmann/data-analysis-environment:python3.8

LABEL maintainer="Michael Wittmann <michael.wittmann@tum.de>"

# Install poetry
WORKDIR /tmp

COPY pyproject.toml ./

RUN apt-get update && apt-get install -y --no-install-recommends llvm-10 llvm-10-dev

RUN python3 -m venv .venv && source .venv/bin/activate && poetry install -v

RUN jupyter contrib nbextension install --user
RUN jupyter nbextensions_configurator enable --user

# Set working directory
WORKDIR /home/ubuntu




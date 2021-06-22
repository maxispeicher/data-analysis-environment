FROM micwittmann/data-analysis-environment:python3.8

LABEL maintainer="Michael Wittmann <michael.wittmann@tum.de>"

# Install poetry
WORKDIR /tmp

COPY pyproject.toml ./

RUN apt-get update && apt-get install -y --no-install-recommends llvm-10 llvm-10-dev

RUN pip3 install -U pip wheel && pip3 install llvmlite PyYaml==5.4.1 \
  && poetry config virtualenvs.create false \
  && poetry install --no-interaction --no-ansi

RUN jupyter contrib nbextension install --user
RUN jupyter nbextensions_configurator enable --user

# Set working directory
WORKDIR /home/ubuntu




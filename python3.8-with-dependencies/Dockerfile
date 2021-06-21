FROM micwittmann/data-analysis-environment:python3.8

LABEL maintainer="Michael Wittmann <michael.wittmann@tum.de>"

# Install poetry
WORKDIR /tmp

COPY pyproject.toml ./

RUN apt-get update && apt-get install llvm-9 llvm-9-dev && llvm-config --libs

RUN pip3 install -U pip wheel && pip3 install llvmlite \
  && poetry config virtualenvs.create false \
  && poetry install --no-interaction --no-ansi

RUN jupyter contrib nbextension install --user
RUN jupyter nbextensions_configurator enable --user

# Set working directory
WORKDIR /home/ubuntu




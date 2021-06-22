FROM micwittmann/data-analysis-environment:python3.8

LABEL maintainer="Michael Wittmann <michael.wittmann@tum.de>"

RUN apt-get update && apt-get install -y --no-install-recommends llvm-10 llvm-10-dev python3.8-venv
# Install poetry
WORKDIR /tmp

ENV VIRTUAL_ENV=/opt/venv
RUN python3.8 -m venv $VIRTUAL_ENV
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

COPY pyproject.toml ./

RUN poetry install -v

RUN jupyter contrib nbextension install --user
RUN jupyter nbextensions_configurator enable --user

# Set working directory
WORKDIR /home/ubuntu




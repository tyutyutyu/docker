FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu-22.04

USER vscode

RUN curl https://pyenv.run | bash

RUN echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
RUN echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc

ARG PYTHON_VERSION=3.11.5
RUN ~/.pyenv/bin/pyenv install "${PYTHON_VERSION}"
RUN ~/.pyenv/bin/pyenv global "${PYTHON_VERSION}"

RUN curl -sSL https://install.python-poetry.org | python3 -

RUN echo "poetry env use ${PYTHON_VERSION}" >> ~/.bashrc

ARG GIT_NAME
ARG GIT_EMAIL
RUN git config --global user.name "${GIT_NAME}"
RUN git config --global user.email "${GIT_EMAIL}"

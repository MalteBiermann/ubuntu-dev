FROM ubuntu:noble@sha256:72297848456d5d37d1262630108ab308d3e9ec7ed1c3286a32fe09856619a782
# sha256:a04dc4851cbcbb42b54d1f52a41f5f9eca6a5fd03748c3f6eb2cbeb238ca99bd
# sha256:3afff29dffbc200d202546dc6c4f614edc3b109691e7ab4aa23d02b42ba86790

# Keeps Python from generating .pyc files in the container
ENV PYTHONDONTWRITEBYTECODE=1

# Turns off buffering for easier container logging
ENV PYTHONUNBUFFERED=1

RUN apt-get update

RUN apt-get install -y python3
RUN apt-get install -y bash git ssh tmux tmate zsh

RUN apt-get clean -y

ARG USERNAME=appuser
ARG USER_UID=1001
ARG USER_GID=$USER_UID
ARG WS='/workspace'


# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

RUN mkdir $WS
RUN chown -R $USERNAME $WS
USER $USERNAME

# WORKDIR $WS
# COPY app.py .

CMD ["/usr/bin/bash"]
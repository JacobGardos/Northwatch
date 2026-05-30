# Inspired By https://blog.hipsquare.net/posts/2022-07-08-exploring-devcontainer
# Keep In Mind The Post Above Is Using An Outdated Image, But Same Logic Applies

# [Optional] Uncomment this section to install additional OS packages.
ARG VARIANT=20-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:1-${VARIANT}

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends neofetch


ARG USERNAME="node"

# ------ Persisting Bash History ------ #
# https://code.visualstudio.com/remote/advancedcontainers/persist-bash-history
RUN SNIPPET="export PROMPT_COMMAND='history -a' && export HISTFILE=/commandhistory/.bash_history" \
    && mkdir /commandhistory \
    && touch /commandhistory/.bash_history \
    && chown -R $USERNAME /commandhistory \
    && echo "$SNIPPET" >> "/home/$USERNAME/.bashrc"



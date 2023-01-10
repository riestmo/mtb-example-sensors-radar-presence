ARG VARIANT="latest"
FROM riestere/modus-linux-24:${VARIANT}

USER root
RUN mkdir /home/vscode
WORKDIR /home/vscode

RUN groupadd -r vscode && \
    useradd --no-log-init -r -g vscode -s /bin/bash vscode && \
    chown -R vscode /home/vscode

USER vscode

RUN mkdir /home/vscode/mtb-workspace
RUN mkdir /home/vscode/mtb-workspace/mtb-example-sensors-radar-presence
WORKDIR /home/vscode/mtb-workspace/mtb-example-sensors-radar-presence

COPY --chown=vscode:vscode . .

RUN make getlibs
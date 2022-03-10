FROM zivgitlab.wwu.io/ag-ohlberger/dune-community/dune-gdt-tutorials/binder:apidocs

# binder wants to set the NB_ vars anyways, so we use it to service both setups
ARG NB_USER
ARG NB_UID

USER root
RUN rm -rf /tutorials && useradd -d /tutorials --shell /bin/bash -u ${NB_UID} -o -c "" -m ${NB_USER}

ENV USER=${NB_USER} \
    HOME=/tutorials

COPY apidocs/* /tutorials/
RUN chown -R ${NB_USER} /tutorials
USER ${NB_USER}

ENTRYPOINT []
WORKDIR /tutorials

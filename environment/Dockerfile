# hash:sha256:a48fae72403c70c8b11f095c0efa01fd757ed88c929197230c901b6bbb0c0cc3
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:24.5.0-0-python3.12.4-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-askpass /

RUN pip install -U --no-cache-dir \
    ipykernel==7.1.0 \
    matplotlib==3.10.8 \
    pandas==2.3.3 \
    seaborn==0.13.2

COPY postInstall /
RUN --mount=type=secret,id=secrets . /run/secrets/secrets \
    && /postInstall

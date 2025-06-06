ARG UV_VERSION=latest

FROM ghcr.io/astral-sh/uv:$UV_VERSION AS uv
FROM mcr.microsoft.com/devcontainers/base:focal

COPY --from=uv --chown=vscode: /uv /uvx /bin/

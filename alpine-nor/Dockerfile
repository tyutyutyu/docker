FROM alpine:3.19.1

ARG UID=1000
ARG GID="${UID}"
ARG USERNAME=duser
ARG GROUP_NAME=dgroup
RUN addgroup -g "${GID}" -S "${GROUP_NAME}" && \
    adduser -u "${UID}" -D -S -G "${GROUP_NAME}" "${USERNAME}"

WORKDIR /work
RUN chown -R "${USERNAME}:${GROUP_NAME}" /work

USER "${USERNAME}"

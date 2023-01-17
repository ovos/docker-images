FROM node:18-alpine

RUN apk update && \
    apk add --no-cache git openssh bash && \
    addgroup -S circleci && adduser -S circleci -G circleci

RUN npm i -g less

ENV PATH $PATH:/usr/local/bin

USER circleci

ENTRYPOINT ["sh"]

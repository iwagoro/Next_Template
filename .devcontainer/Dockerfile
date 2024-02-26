FROM node:21-alpine
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Tokyo
RUN apk update && apk add git curl

WORKDIR /workspace

RUN npx create-next-app@latest my-app \
    --typescript --eslint --app --src-dir \
    --import-alias --use-yarn --tailwind

RUN yarn add react-icons@latest
RUN yarn add firebase@latest

WORKDIR /workspace/my-app

RUN mkdir -p /workspace/my-app/docker
COPY ./ /workspace/my-app/docker

RUN git init
FROM node:alpine

RUN npm install -g browser-sync

WORKDIR /app

CMD ["browser-sync", "start", "--server", "--files", "**/*.html,**/*.css,**/*.js", "--no-notify", "--port", "80"]

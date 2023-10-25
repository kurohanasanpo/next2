FROM mcr.microsoft.com/playwright:v1.39.0-jammy

RUN apt update -y && apt install dnsutils -y

RUN mkdir -p /playwright
WORKDIR /playwright
COPY tests ./tests
COPY package.json playwright.config.ts ./
RUN npm install

ENTRYPOINT [ "npx", "playwright", "test" ]
CMD [ "--trace", "on" ]
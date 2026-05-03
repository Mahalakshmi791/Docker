FROM node:20-alpine3.22 AS builder
LABEL tier="backend"
WORKDIR /app
COPY . .
RUN npm install

FROM node:20-alpine3.22
WORKDIR /app
COPY --from=builder /app .
ENV DB_HOST="mysql-cont"
EXPOSE 8080
RUN addgroup --system expense && \
    adduser --system --ingroup expense --home /app --shell /sbin/nologin expense
USER expense
CMD ["node", "/app/index.js"]
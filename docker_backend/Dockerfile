# -------- stage 1 ---------
FROM node:22-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# -------- stage 2 ---------
FROM node:22-alpine

WORKDIR /app

COPY --from=builder /app /app/

EXPOSE 3000
ENV PORT=3000

CMD [ "node", "index.js" ]

# --- multi stage build is needed to present smaller needed version of the app rather than presenting the whole bloated mostly unused package-ful image -----
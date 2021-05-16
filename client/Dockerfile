FROM node:alpine

WORKDIR /opt/app

ENV NODE_ENV development

COPY package.json yarn.lock ./

RUN set -eux && \
    apk add --no-cache libc6-compat && \
    yarn install --frozen-lockfile

COPY . .

# For production env
# RUN set -eux && \
#     yarn build && \
#     addgroup -g 1001 -S nodejs && \
#     adduser -S nextjs -u 1001 && \
#     chown -R nextjs:nodejs /opt/app/.next

# USER nextjs

EXPOSE 3000

CMD ["yarn", "dev"]

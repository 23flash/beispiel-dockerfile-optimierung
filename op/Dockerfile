FROM docker.io/python:3.11-slim AS builder
  RUN pip install --no-cache-dir mkdocs mkdocs-material
  WORKDIR ./
  COPY . .
  RUN mkdocs build
  FROM docker.io/nginx:alpine
  COPY --from=builder ./site /usr/share/nginx/html
  EXPOSE 80
  CMD ["nginx", "-g", "daemon off;"]

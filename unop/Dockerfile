FROM docker.io/python:3.11
  RUN pip install mkdocs
  RUN pip install mkdocs-material
  WORKDIR /app/project/build
  COPY mkdocs.yml .
  COPY docs ./docs
  COPY . .
  RUN mkdocs build
  RUN apt-get update && apt-get install -y nginx
  RUN cp -r ./site /usr/share/nginx/html
  EXPOSE 80
  CMD ["nginx", "-g", "daemon off;"]

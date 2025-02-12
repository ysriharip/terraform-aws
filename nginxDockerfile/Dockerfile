# Use official Nginx image
FROM nginx:latest

# Install Nginx Prometheus Exporter
RUN apt-get update && apt-get install -y wget ca-certificates \ 
    && wget https://github.com/nginxinc/nginx-prometheus-exporter/releases/download/v0.11.0/nginx-prometheus-exporter_0.11.0_linux_amd64.deb \
    && dpkg -i nginx-prometheus-exporter_0.11.0_linux_amd64.deb 

# Copy the static files to Nginx's default HTML directory
COPY index.html /usr/share/nginx/html/index.html

# Expose ports
EXPOSE 80 9113

# Start Nginx and the Prometheus Exporter
CMD ["sh", "-c", "nginx && nginx-prometheus-exporter -nginx.scrape-uri=http://127.0.0.1/nginx_status"]


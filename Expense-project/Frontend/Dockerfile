FROM nginx:stable-alpine

# Remove default nginx config
RUN rm /etc/nginx/conf.d/default.conf

COPY . /usr/share/nginx/html/
COPY expense.conf /etc/nginx/conf.d/expense.conf

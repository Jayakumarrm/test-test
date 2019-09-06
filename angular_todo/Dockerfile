# Note run `npm build` before bilding image
# Ngnix base image
FROM nginx:1.15.0-alpine

# copy build from the 'build environment'
COPY ./dist/todo /var/www/todo

# Remove nginx default configuration file
RUN rm /etc/nginx/conf.d/default.conf

# Copy a configuration file from the current directory
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./nginx/sites.conf /etc/nginx/sites-enabled/sites.conf

# expose port 80
EXPOSE 80

# run nginx
CMD ["nginx", "-g", "daemon off;"]

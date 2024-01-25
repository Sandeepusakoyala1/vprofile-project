FROM nginx
LABEL "project"="vprofile"
LABEL "Author"="Sandeep"

# we have to remove the default conf file 
RUN rm -rf /etc/nginx/conf.d/default.conf
# move create a own conf file and move it to below path 
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf

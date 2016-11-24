FROM elct9620/nginx-pagespeed

COPY pagespeed /etc/nginx/conf.d/pagespeed.conf

ENV TZ=Asia/Bangkok
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

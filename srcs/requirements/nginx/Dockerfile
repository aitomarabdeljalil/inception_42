# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: aait-oma <aait-oma@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/05/28 13:50:47 by aait-oma          #+#    #+#              #
#    Updated: 2023/05/28 16:55:28 by aait-oma         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM debian:buster

RUN  apt-get update -y \
	&& apt-get install nginx -y \
    && apt-get install openssl -y \
    && openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt -subj "/CN=MA"\
	&& mkdir -p /var/www/website

COPY /conf/default /etc/nginx/sites-available

CMD ["nginx", "-g", "daemon off;"]

# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Dockerfile                                         :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: wquinoa <wquinoa@student.42.fr>            +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/09/13 17:53:39 by kwillum           #+#    #+#              #
#    Updated: 2020/09/23 19:21:24 by wquinoa          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

FROM alpine

RUN apk update
RUN apk add grafana --repository=http://dl-3.alpinelinux.org/alpine/edge/testing/

COPY influxdb-datasource.yaml /usr/share/grafana/conf/provisioning/datasources/influxdb.yaml
COPY dashboards.yaml /usr/share/grafana/conf/provisioning/dashboards/dashboards.yaml
COPY ./json/* /var/lib/grafana/dashboards/

EXPOSE	3000
ENTRYPOINT [ "grafana-server", "--homepath=/usr/share/grafana" ]
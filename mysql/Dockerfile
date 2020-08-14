FROM mysql

RUN apt install -y tzdata

COPY init.sql /docker-entrypoint-initdb.d/

ENV TZ Asia/Ho_Chi_Minh
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

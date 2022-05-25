FROM docker.elastic.co/elasticsearch/elasticsearch:7.13.2

RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install --batch repository-s3

COPY --chown=elasticsearch:elasticsearch elasticsearch.yml /usr/share/elasticsearch/config/

RUN echo "<S3-secret-key>" | bin/elasticsearch-keystore add --stdin --force s3.client.default.secret_key
RUN echo "<S3-access-key>" | bin/elasticsearch-keystore add --stdin --force s3.client.default.access_key

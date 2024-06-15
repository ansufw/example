# ELK Service

source: https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose

## How to Use

1. Run `docker compose up`
2. Run `docker cp <compose-project-name>``-es01-1:/usr/share/elasticsearch/config/certs/ca/ca.crt /tmp/.`
3. If the username and password are default, run `curl --cacert /tmp/ca.crt -u elastic:changeme https://localhost:9200`
4. Try login Kibana via browser, run `http://localhost:5601` and if you have not yet changed the default, use `elastic` and `changeme` as username and password.

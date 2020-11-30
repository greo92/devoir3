FROM python:latest

RUN pip3 install psycopg2

COPY config.py CeQueJeVeux/
COPY tests_integration.py CeQueJeVeux/
COPY utils_postgres.py CeQueJeVeux/
COPY __init__.py CeQueJeVeux/
COPY __main__.py CeQueJeVeux/

EXPOSE 5432

RUN wget https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh -P /
RUN chmod +x /wait-for-it.sh
ENTRYPOINT ["/wait-for-it.sh", "db:5432", "--"]

CMD ["python", "-m", "CeQueJeVeux"]
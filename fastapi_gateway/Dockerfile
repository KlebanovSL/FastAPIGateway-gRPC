FROM python:3.11-slim

EXPOSE 8000

WORKDIR /fastapi-gateway

COPY poetry.lock pyproject.toml ./

RUN python -m pip install --no-cache-dir poetry &&\
    poetry config virtualenvs.in-project true &&\
    poetry install --no-interaction --no-ansi --no-root

COPY . .

RUN chmod +x entrypoint.sh

ENTRYPOINT [ "./entrypoint.sh" ]
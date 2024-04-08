# set up the container.
FROM python:3.10-alpine

# set the UID and GID as environment variables
ARG UID
ARG GID
ENV UID=${UID} GID=${GID}

COPY .containers/fastapi/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# set the working dir.
WORKDIR /app

# copy the rest of the app
COPY ./app /app

# command to run the app using uvicorn.
# CMD ["echo", "test"]
CMD ["uvicorn","main:app","--host","0.0.0.0","--port","8000"]

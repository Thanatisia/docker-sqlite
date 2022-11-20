# Dockerfile
# for
# SQLite3

# Pull Base Distribution Image
FROM alpine

# Install packages
RUN apk add --update \
    sqlite bash

# Create Database folder
RUN mkdir /db

# Set working directory
WORKDIR /db

# Set Entry point command to run
ENTRYPOINT ["sqlite3"]

# Run command/parameter appended to the entry point
# CMD ["test.db"]



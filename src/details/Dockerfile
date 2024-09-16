FROM ruby:3.3.0-slim

WORKDIR /opt/microservices

COPY . .

RUN bundle install

ARG SERVICE_VERSION_ARG=v1

ARG ENABLE_BOOK_SERVICE_ARG=false

ENV SERVICE_VERSION=${SERVICE_VERSION_ARG:-v1}

ENV ENABLE_BOOK_SERVICE=${ENABLE_BOOK_SERVICE_ARG:-false}

EXPOSE 9080

RUN useradd -u 1000 -m myuser

USER myuser

CMD ["ruby", "details.rb", "9080"]
FROM ruby:3.1-slim-bullseye AS base

WORKDIR /app

ENV BUNDLE_DEPLOYMENT=true
ENV BUNDLE_WITHOUT="development test"

COPY Gemfile* .

RUN apt-get update -y
RUN apt-get install -y build-essential
RUN bundle install


FROM ruby:3.1-slim-bullseye AS production

WORKDIR /app

ENV BUNDLE_DEPLOYMENT=true
ENV BUNDLE_WITHOUT="development test"

ENV RAILS_ENV=production

COPY . .
COPY --from=base /app/vendor/bundle vendor/bundle

CMD ["bin/rails"]

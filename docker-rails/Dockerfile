FROM ruby:3.0.2

ENV APP_PATH /docker-rails

ENV BUNDLE_VERSION 2.3.17

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs vim

RUN gem install bundler --version "$BUNDLE_VERSION"

WORKDIR $APP_PATH

COPY Gemfile Gemfile.lock $APP_PATH/

RUN bundle install

COPY . $APP_PATH

EXPOSE 3000

FROM ruby:2.7.2

ENV LANG=C.UTF-8 \
  TZ=Asia/Tokyo

WORKDIR /app
RUN apt-get update -qq && apt-get install -y nodejs default-mysql-client
RUN bundle config set --global force_ruby_platform true
COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
RUN bundle install

# Start the main process.
CMD ["rails", "server", "-b", "0.0.0.0"]
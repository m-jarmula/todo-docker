FROM ruby:2.6.0
RUN apt-get update -qq && apt-get install -y nodejs postgresql-client
WORKDIR /myapp
COPY ./Gemfile ./Gemfile
COPY ./Gemfile.lock ./Gemfile.lock
RUN gem install bundler:2.0.2
RUN gem update --system
RUN bundle install
COPY . .
EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]

# The below image is created out of the Dockerfile.base
# It has the dependencies already installed so that codespace will boot up fast
FROM ghcr.io/chatwoot/chatwoot_codespace:latest

# Do the set up required for chatwoot app
WORKDIR /workspace
COPY . /workspace

RUN mkdir -p "$(rbenv root)"/plugins && \
    git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build && \
    cd "$(rbenv root)"/plugins/ruby-build && git pull && \
    rbenv install 3.3.3 && rbenv global 3.3.3 && rbenv versions
RUN yarn && gem install bundler && bundle install

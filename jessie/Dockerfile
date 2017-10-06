FROM elixir

# update jessie kernel and install vim
RUN apt update \
    && apt install -y vim

# updates local.hex and installs phoenix framework and rebar
RUN mix local.hex --force \
    && mix archive.install --force https://github.com/phoenixframework/archives/raw/master/phx_new.ez \
    && mix local.rebar --force

# installs nodejs from PPA
RUN cd ~ \
    && curl -sL https://deb.nodesource.com/setup_6.x -o nodesource_setup.sh \
    && chmod +x nodesource_setup.sh \
    && bash nodesource_setup.sh \
    && apt install nodejs \
    && apt install build-essential #\

EXPOSE 4000

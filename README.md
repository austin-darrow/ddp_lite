# README

Installation Commands
--------------

__Update Packages__
```
apt update && apt upgrade -y
```

__Install Ruby__
```
apt install gcc make libssl-dev libreadline-dev zlib1g-dev libsqlite3-dev curl git
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
mkdir -p "$(rbenv root)"/plugins
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
rbenv install 3.1.2
rbenv global 3.1.2
```

__Install Rails & Other Dependencies__
```
gem install rails
apt install yarn
```

__Install App__


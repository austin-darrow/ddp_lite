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
```
cd
git clone https://github.com/austin-darrow/ddp\_lite
cd ddp\_lite
bundle install
```

Starting the Web & App Servers
------------------
```
make nginx_restart
make nginx_reload
make nginx_status
rails s -d &       # Starts the server as a daemon; must be run from inside ~/ddp_lite 
```

Stopping the Web & App Servers
-------------------
Use the following command to find the app server process id:
```
ps -aux | grep puma | awk 'NR==1{{print $2}}'
```

Use the following command to stop the app server (running on port 3000):
```
kill -9 $(lsof -i tcp:3000 -t)
```

User the following command to stop the web server:
```
sudo systemctl stop nginx
```


Editing Web Server Config
-------------
```
make nginx_edit_conf
```

Editing App Pages
--------
- HTML pages are in ddp\_lite/app/views/pages
- Header/footer are in ddp\_lite/app/views/shared
- Main HTML metadata is in ddp\_lite/app/views/layouts/application.html.erb
- CSS is in ddp\_lite/app/assets/stylesheets/main.css
- Images are in ddp\_lite/app/assets/images

#   Ruby 安裝教學

1.  到 https://rvm.io/ 安裝 ruby version manager，

    網頁上有兩行指令，複製他然後開一個 terminal 再貼上去執行

    安裝完後，家目錄下會出現 .rvm 這個目錄，以後要安裝不同版本的 ruby 或 ruby 的套件，都在這個資料夾裡

2.  重新讀取 .bashrc，這樣子就可以執行 `rvm` 這個指令了

        $ source .bashrc

3.  用 rvm 安裝 ruby

    rvm 全名是 ruby version manager，是拿來裝 ruby 的

    畢竟 ruby 直譯器有用 C 寫的，叫 MRI (Matz's Ruby Interpreter) 、也有用 java 寫的，叫 jruby，以下用的是 MRI

    用 rvm 看一下最新版本的 ruby 是多少

        $ rvm list known

    然後安裝該版本

        $ rvm install 2.1.0

4.  用 gem 安裝 ruby 的套件，像 rails

    gem 是一個 ruby 的套件，它的功能就是裝其他的套件，所以裝完 rvm 就有附 gem 在裡面了

        $ gem install rails 

#   Rails 安裝教學

1.  開一個資料夾，然後建立一個空的網站

        $ mkdir example
        $ cd example
        $ rails new .

2.  把這網站需要用到的 ruby 套件裝一裝

    bundler 是一個 ruby 的套件，它的功能就是一次裝完所有需要的套件，所以裝完 rvm 就有附 bundler 在裡面了

        $ bundle install

3.  Run 一下你的網站吧

        $ rails server
        => Booting WEBrick
        => Rails 3.2.15 application starting in development on http://0.0.0.0:3000
        => Call with -d to detach
        => Ctrl-C to shutdown server
        [2014-06-12 19:25:29] INFO  WEBrick 1.3.1
        [2014-06-12 19:25:29] INFO  ruby 2.0.0 (2013-11-22) [x86_64-linux]
        [2014-06-12 19:25:29] INFO  WEBrick::HTTPServer#start: pid=9797 port=3000

    開啟你的 chromium 或 firefox，貼上網址 http://0.0.0.0:3000

以下的步驟可選

3.  用 git 做版本控管

    建立一個空的 git

        $ git init

    新增第一個 commit 

        $ git add .
        $ git commit -m "Init."

#   Heroku 安裝教學

1.  到官網 https://www.heroku.com/ 註冊一個帳號

2.  到官網 https://toolbelt.heroku.com/debian 安裝 heroku 這個程式

    其實照著官網的步驟做即可，以下是延續「Rails 安裝教學」的步驟

        $ wget -qO- https://toolbelt.heroku.com/install-ubuntu.sh | sh

3.  登入 heroku

        $ heroku login
        Enter your Heroku credentials.
        Email: adam@example.com
        Password:
        Could not find an existing public key.
        Would you like to generate one? [Yn]
        Generating new SSH public key.
        Uploading ssh public key /Users/adam/.ssh/id_rsa.pub

4.  建一個 heroku app

        $ cd example
        $ heroku create
        Creating stark-fog-398... done, stack is cedar
        http://stark-fog-398.herokuapp.com/ | git@heroku.com:stark-fog-398.git
        Git remote heroku added

5.  佈署 rails 到 heroku

        $ git push heroku master 

6.  看一下你的網站吧

    網址在第四步時可以看到

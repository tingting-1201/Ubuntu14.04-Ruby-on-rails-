# Ubuntu14.04-Ruby-on-rails
ubuntu下rails环境搭建
1.
安装系统需要的包 ，在lnux终端输入下面命令
sudo apt-get install -y build-essential openssl curl libcurl3-dev libreadline6 libreadline6-dev
 git zlib1g zlib1g-dev libssl-dev libyaml-dev libxml2-dev libxslt-dev autoconf automake libtool 
 imagemagick libmagickwand-dev libpcre3-dev libsqlite3-dev mysql-client libmysqlclient-dev postgresql
2.
安装RVM
$ curl -L https://get.rvm.io | bash -s stable
等待一段时间后就可以成功安装好 RVM。
然后，载入 RVM 环境（新开 Termal 就不用这么做了，会自动重新载入的）

$ source ~/.rvm/scripts/rvm
检查一下是否安装正确

$ rvm -v
rvm 1.17.3 (stable) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]

4.
设置 Ruby 版本
RVM 装好以后，需要执行下面的命令将指定版本的 Ruby 设置为系统默认版本

$ rvm 1.9.3 --default
同样，也可以用其他版本号，前提是你有用 rvm install 安装过那个版本
这个时候你可以测试是否正确

$ ruby -v
ruby 1.9.3p290 (2011-07-09 revision 32553) [x86_64-darwin10.8.0]  --提示信息
$ gem -v
1.8.6 --提示信息
5.
安装 Rails 环境
上面 3 个步骤过后，Ruby 环境就安装好了，接下来安装 Rails

在安装Rails 之前，我们先创建一个gemset，并把rails 安装在这个gemset中，这样，就可以现实Rails多版本的安装和管理

$ rvm use 1.9.3
 在创建gemset前，必须先选定Ruby版本，这里我们要安装Rails 3.2.9，故选择Ruby1.9.3

$ rvm create gemseet rails3
这样我们就创建好了一个属于Ruby1.9.3的Gemseet，名叫 rails3

$ rvm use 1.9.3@rails3
指定使用Ruby版本为1.9.3，并使用1.9.3下面的rails3的Gemset

$ gem install  rails -v 3.2.9
这一补会比花费较长的时间

6.检测安装
下面我们将检测我们的Ruby on Rails环境搭建是否正确

$ rvm use 1.9.3@rails3
Using /home/panaoke/.rvm/gems/ruby-1.9.3-p362 with gemset rails3Using /home/panaoke/.rvm/gems/ruby-1.9.3-p362 with gemset rails3 --提示信息
注意，我们每次打开命令行，都要执行上面的命令来选择Ruby版本和Rails版本

$ ruby -v
ruby 1.9.3p362 (2012-12-25 revision 38607) [x86_64-linux] --提示信息
如出现上面提示信息，则表示Ruby1.9.3版本安装正确

$ rails -v
Rails 3.2.9 --提示信息
如出现上面提示信息，则表示Rails 3.2.9 版本安装正确

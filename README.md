<img src="http://www.zold.io/logo.svg" width="64px" height="64px"/>

[![EO principles respected here](http://www.elegantobjects.org/badge.svg)](http://www.elegantobjects.org)
[![Managed by Zerocracy](https://www.0crat.com/badge/C91QJT4CF.svg)](https://www.0crat.com/p/C91QJT4CF)
[![DevOps By Rultor.com](http://www.rultor.com/b/yegor256/Zold)](http://www.rultor.com/p/yegor256/Zold)
[![We recommend RubyMine](http://www.elegantobjects.org/rubymine.svg)](https://www.jetbrains.com/ruby/)

[![Build Status](https://travis-ci.org/zerocracy/zold.svg)](https://travis-ci.org/zerocracy/zold)
[![Build status](https://ci.appveyor.com/api/projects/status/ypctxm5ohrtp2kr4?svg=true)](https://ci.appveyor.com/project/yegor256/zold)
[![PDD status](http://www.0pdd.com/svg?name=zerocracy/zold)](http://www.0pdd.com/p?name=zerocracy/zold)
[![Gem Version](https://badge.fury.io/rb/zold.svg)](http://badge.fury.io/rb/zold)
[![Test Coverage](https://img.shields.io/codecov/c/github/zerocracy/zold.svg)](https://codecov.io/github/zerocracy/zold?branch=master)

[![Dependency Status](https://gemnasium.com/zerocracy/zold.svg)](https://gemnasium.com/zerocracy/zold)
[![Maintainability](https://api.codeclimate.com/v1/badges/7489c1d2bacde40ffc09/maintainability)](https://codeclimate.com/github/zerocracy/zold/maintainability)

**NOTICE**: It's an experiment and a very early draft! Please, feel free to
submit your ideas or pull requests.

Here is the [White Paper](https://latexonline.cc/compile?git=https%3A%2F%2Fgithub.com%2Fyegor256%2Fzold&target=wp%2Fwp.tex&command=pdflatex&trackId=1520158941887).

The license is [MIT](https://github.com/zerocracy/zold/blob/master/LICENSE.txt).

## How to Use

Install Ruby 2.2+, [Rubygems](https://rubygems.org/pages/download), and then run:

```bash
$ sudo apt-get install ruby-dev rubygems zlib1g-dev
$ gem install zold
```

Then, either run it as a node:

```bash
$ zold node
```

For more options and commands just run:

```bash
$ zold --help
```

You will need PGP keys in `~/.ssh`. To generate them (if you don't have them yet):

```bash
$ ssh-keygen -t rsa -b 4096
```

First, create a wallet (instead of `5f96e731e48ae21f` there will be your
person wallet number, use it everywhere below):

```bash
$ zold create
5f96e731e48ae21f
```

Then, give its number to your friend, who is going to pay you.
When the payment is sent, ask him or her for the number of the wallet
the payment has been sent from and then fetch that wallet
(let's say it is `5555444433332222`):

```bash
$ zold fetch 5555444433332222
5.00 ZLD added to 5f96e731e48ae21f: To my friend!
```

Now, you have the money in your wallet!

Next, you can pay your friend back:

```bash
$ zold pay 5f96e731e48ae21f 5555444433332222 2.50 'Here is a refund'
-2.50 ZLD added to 5f96e731e48ae21f: Here is a refund
```

Finally, you have to push your wallet to the network so that your friend
knows about the payment:

```bash
$ zold push 5f96e731e48ae21f
```

That's it.

You also can contribute to Zold by running a node on your server.
In order to do that just run:

```bash
$ zold node --invoice=5f96e731e48ae21f
```

Grateful users of the system will pay "taxes" to your wallet for processing
of their transactions.

## How to Contribute

It is a Ruby command line gem. First, install
[Ruby](https://www.ruby-lang.org/en/documentation/installation/) 2.3+,
[Rubygems](https://rubygems.org/pages/download),
and
[Bundler](https://bundler.io/).
Then:

```bash
$ bundle update
$ rake
```

The build has to be clean. If it's not, [submit an issue](https://github.com/zerocracy/zold/issues).

Then, make your changes, make sure the build is still clean,
and [submit a pull request](https://www.yegor256.com/2014/04/15/github-guidelines.html).

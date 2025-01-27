# (RVM) Ruby Version Manager

## RVM Ruby installation fails on macOS

### Error

```bash
Error running '__rvm_make -j8',
please read /Users/.../.rvm/log/1737956978_ruby-3.0.0/make.log

There has been an error while running make. Halting the installation.
```

### Solution #1

Make sure to supply `--with-openssl-dir` parameter.

For simplicity you can install OpenSSL with Homebrew:

```bash
brew update
brew install openssl@3
```

And then prefix the openssl@3 path with Homebrew:

```bash
rvm install 3.4.1 --with-openssl-dir=$(brew --prefix openssl@3)
```

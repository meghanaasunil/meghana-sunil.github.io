# Local Jekyll Setup Guide

## ⚠️ Important: Ruby Version Requirement

Your current Ruby version (2.6.10) is too old for the latest Jekyll dependencies. You have two options:

### Option 1: Upgrade Ruby (Recommended)

**Using Homebrew (macOS):**
```bash
# Install Homebrew if you don't have it: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Ruby 3.x
brew install ruby

# Add to PATH (add to ~/.zshrc)
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

# Install bundler
gem install bundler

# Install dependencies
bundle install

# Run Jekyll
bundle exec jekyll serve
```

**Using rbenv (Alternative):**
```bash
# Install rbenv
brew install rbenv ruby-build

# Install Ruby 3.2+
rbenv install 3.2.0
rbenv global 3.2.0

# Install bundler and dependencies
gem install bundler
bundle install
bundle exec jekyll serve
```

### Option 2: Use GitHub Pages Build (No Local Setup Needed)

Since this is a GitHub Pages site, you can:
1. Push changes to GitHub
2. GitHub will automatically build and deploy
3. View at https://meghanaasunil.github.io

No local Jekyll setup required!

### Option 3: Use Docker (If you have Docker)

```bash
docker run --rm -it -v "$PWD":/srv/jekyll -p 4000:4000 jekyll/jekyll:4.2.2 jekyll serve
```

## Quick Test (After Ruby Upgrade)

```bash
# Check Ruby version (should be 3.0+)
ruby --version

# Install bundler
gem install bundler

# Install dependencies
bundle install

# Run server
bundle exec jekyll serve

# View at http://localhost:4000
```

## Troubleshooting

- **Permission errors**: Use `--user-install` flag or upgrade Ruby
- **Bundler conflicts**: Try `bundle update --bundler`
- **Stop server**: Press `Ctrl+C`
- **Port in use**: Use `bundle exec jekyll serve --port 4001`


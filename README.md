# [bfrangi.github.io](https://bfrangi.github.io)

Code for Bernat Frangi's personal site 🙌.

## Table of contents
- [bfrangi.github.io](#bfrangigithubio)
  - [Table of contents](#table-of-contents)
  - [Setup for local development](#setup-for-local-development)
  - [Running the site locally](#running-the-site-locally)

## Setup for local development 

As per the instructions on the official Jekyll Docs [[1]], the setup
for local development in Ubuntu is as follows:

1.  Install Ruby and other requirements:

    ```sh
    sudo apt-get install ruby-full build-essential zlib1g-dev
    ```

2.  Set up a gem installation directory for your user account to avoid
    installing gems as the root user (note that if you are using
    `zsh`, you should add these lines to `~/.zshrc` instead of
    `~/.bashrc`):
    
    ```sh
    echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
    source ~/.bashrc
    ``` 
3.  Install Jekyll and Bundler:

    ```sh
    gem install jekyll bundler
    ```

## Running the site locally

1.  Navigate to the root directory of the project and run the following command to install dependencies:

    ```sh
    bundle install
    ```

2.  Run the following command to build the site and make it available on a local server:

    ```sh
    bundle exec jekyll serve --livereload
    ```

3.  Open a browser and navigate to [`http://localhost:4000`](http://localhost:4000) to see the site.


[1]: https://jekyllrb.com/docs/installation/ubuntu/
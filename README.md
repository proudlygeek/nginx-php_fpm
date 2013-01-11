# Vagrantfile for nginx + php_fpm

1. Clone the repo
  ```bash
  git clone git@github.com:proudlygeek/nginx-php_fpm.git
  ```

2. **Install Vagrant**
  ```bash
  gem install vagrant
  ```

3.  **Download a template box (here's a [list][1])**
  ```bash
  vagrant box add  https://github.com/downloads/roderik/VagrantQuantal64Box/quantal64.box
  ```

4.  **Install Librarian and download the cookbooks**
  ```bash
  gem install librarian
  ```
  ```bash
  librarian-chef install
  ```

5.  **Provision the box**
  ```bash
  vagrant box up
  ```

6.  **Login via ssh and start customizing!**
  ```bash
  vagrant ssh
  ```
  

[1]: http://www.vagrantbox.es

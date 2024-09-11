[![Build Status](https://runbot.odoo.com/runbot/badge/flat/1/master.svg)](https://runbot.odoo.com/runbot)
[![Tech Doc](https://img.shields.io/badge/master-docs-875A7B.svg?style=flat&colorA=8F8F8F)](https://www.odoo.com/documentation/master)
[![Help](https://img.shields.io/badge/master-help-875A7B.svg?style=flat&colorA=8F8F8F)](https://www.odoo.com/forum/help-1)
[![Nightly Builds](https://img.shields.io/badge/master-nightly-875A7B.svg?style=flat&colorA=8F8F8F)](https://nightly.odoo.com/)

Odoo
----

Odoo is a suite of web based open source business apps.

The main Odoo Apps include an <a href="https://www.odoo.com/page/crm">Open Source CRM</a>,
<a href="https://www.odoo.com/page/website-builder">Website Builder</a>,
<a href="https://www.odoo.com/page/e-commerce">eCommerce</a>,
<a href="https://www.odoo.com/page/warehouse">Warehouse Management</a>,
<a href="https://www.odoo.com/page/project-management">Project Management</a>,
<a href="https://www.odoo.com/page/accounting">Billing &amp; Accounting</a>,
<a href="https://www.odoo.com/page/point-of-sale">Point of Sale</a>,
<a href="https://www.odoo.com/page/employees">Human Resources</a>,
<a href="https://www.odoo.com/page/lead-automation">Marketing</a>,
<a href="https://www.odoo.com/page/manufacturing">Manufacturing</a>,
<a href="https://www.odoo.com/#apps">...</a>

Odoo Apps can be used as stand-alone applications, but they also integrate seamlessly so you get
a full-featured <a href="https://www.odoo.com">Open Source ERP</a> when you install several Apps.

# odoo14 project(oca)

Use docker https://github.com/minhng92/odoo-14-docker-compose?tab=readme-ov-file  

Install Odoo
========

## OS

Update

```sh
sudo add-apt-repository universe
sudo add-apt-repository "deb http://mirrors.kernel.org/ubuntu/ xenial main"
sudo apt-get update
sudo apt-get upgrade -y
```

## Python

Install Python 3.8

```sh
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.8
python3.8 --version (check version)
```

## Virtual Environments

Install Virtual Environments

```sh
pip install virtualenv
virtualenv --version (check version)
virtualenv -p /usr/bin/python3.8 python-venv/odoo14
```

## Git

### Install Git

```sh
sudo apt update
sudo apt install git
git --version (check version)
```

### Connecting to GitHub with SSH

[Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Odoo

### Install dependencies

```sh
sudo apt-get install python3 python3-pip build-essential wget python3-dev python3-venv python3-wheel libxslt-dev libzip-dev libldap2-dev libsasl2-dev python3-setuptools node-less libpng12-0 gdebi -y
sudo apt-get install nodejs npm -y
sudo npm install -g rtlcss
```
Or run file setup  

### Install Wkhtmltopdf
```sh
wget https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox_0.12.6-1.focal_amd64.deb
sudo apt install ./wkhtmltox_0.12.6-1.focal_amd64.deb
wkhtmltopdf --version (check version)
```

### Clone code in github

```sh
git clone --branch 14.0 git@github.com:odoo/odoo.git
source python-venv/odoo14/bin/activate
pip install -r /odoo/requirements.txt
deactivate
```

### Install PostgreSQL Server

```sh
sudo apt-get install postgresql postgresql-server-dev-all -y
sudo su - postgres -c "createuser -s user_dang_nhap_vao_may"
```

### Install Eclipse

```sh
sudo snap install --classic eclipse
sudo apt install default-jre
```

Config to run on Eclipse
========

Cài đặt pydev trong `help -> eclipse marketplace`  
Import folder odoo vào trong workspace của eclipse và bật pydev project với môi trường python3.8 vừa tạo `python-venv/odoo14`

## Run odoo bin
Trong `odoo/odoo bin` run với python run

## Config 
Để config các thông số vào `Run configurations -> Arguments` thay đổi các thông số dưới đây
```sh
--addons-path=/home/nkduyen/odoo/addons,/home/nkduyen/eclipse-workspace/odoo-basic

--log-sql
--load=base,web
--http-port=8084
```
addons-path dùng để nhận dạng folder chứa app, module trong odoo, các thông số còn lại có thể config tùy theo nhu cầu sử dụng.  
Config xong `Apply -> Run` 

## Run
Config xong `Apply -> Run`   
Vào trình duyệt gõ đường dẫn `http://127.0.0.1/< --http-port >`  
Tạo database và sử dụng




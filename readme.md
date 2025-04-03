## Install System Dependencies

For **Fedora**,( if using **ubuntu/wsl** use **apt** instead of **dnf** )

```shell
sudo dnf update -y
```

#### Install Python & Pip

Fedora ships with Python, but ensure you have Python 3.10+ (recommended for Django 5+):

```shell 
sudo dnf install -y python3 python3-pip python3-virtualenv
```

#### Install PostgreSQL

```shell
sudo dnf install -y postgresql-server postgresql-contrib
```

Initialize and start PostgreSQL:

```shell
sudo postgresql-setup --initdb --unit postgresql sudo systemctl enable --now postgresql
```

#### Verify Installation


```shell 
python3 --version pip3 --version psql --version
```

---

### Setup Venv

```shell
python3 -m venv venv
source venv/bin/activate
```

### For Postgress (Authintication Issue)

Edit `pg_hba.conf` at `\etc\postgress\data` or `\var\lib\pgsql\data`

change host to **md5**

### Backend
Backend service is responsible for adding the given values to databse. Backend service is written is NodeJS, Hence we need to isntall NodeJS.

**Developer has chosen NodeJS, Check with developer which version of NodeJS is needed. Developer has set a contest taht it can work wth NodeJS  >20**

Install Ndoe JS, By default NodeJS 16 is available, we would like to enable 20 version and isntall this.

**You can list modules by using dnf module list**

```

dnf module diable nodejs -y
```
```

dnf module enable nodejs:20 -y
```

```
dnf install nodejs -y
```

Configure the application.

Add application User
```

useradd expense
```

User enpense is a function / daemon user to run the application. Aprt from that we don't use this user to login to server.

Also, username expense has been picked because it more suites to our prokect mane.

we keep application is one standard location. THis is usual practice that runs in the organization.

Lets setup an app directory.

```

mkdir /app
```

we need to setup a new service in systemd so systemctl can manage this service

Setup SystemD Expense Backend Service

```

vim /etc/systemd/system/backend.service
```

```

[Unit]
Description = Backend Service

[Service]
User=expense
Environment=DB_Host="<MYSQL-SERVER-IPADDRESS>"
ExecStart=/bin/node /app/index.js
SyslogIdentifier=backend

[Install]
WantedBy=multi-user.target
```

**Note
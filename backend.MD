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


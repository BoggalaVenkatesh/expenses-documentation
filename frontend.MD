# Frontend

The frontend is the service is Expense to serve the web content over Nginx. This will have the web frame for the web application.

This is a static and to serve static content we need a web server. THis server

Develop has chosen Nginx as a web server and thus we will install Nginx web Server.

Install Nginx
```

dnf isntall nginx -y
```
Enable nginx
```

systemctl enable nginx
```

Start nginx
```

systemctl start nginx
```

**Try to access the service ocne over the browser and ensure you get some default content**


Remove the default content that web server in serving.
```

rm -rf /usr/share/nginx/html
```

Download the frontend content
```

curl -o /tmp/frontend.zip https://expense-builds.s3.us-east-1.amazonaws.com/expense-frontend-v2.zip
```

Extract the frontend content.
```
cd /usr/share/nginx/html
```
```

unzip /tmp/fronend.zip
```

**Try to access the nginx service once more over the browser and ensure you get expense content.**

create Nginx Reverse Proxy Configuration.
```

vim /etc/nginx/default.d/expense.Conf
```
Add the following content
```

proxy_http_version 1.1;

location /api/ {proxy_pass http://localhost:8080/; }

location /health {
    stub_status on;
    access_log off;
}
```

**Ensure you replace the localhost with the actual ip address of backend component server. Word localhost is just used to avoid the failures on the Nginx Server.**

Restart Nginx service to load the changes of the configuration.

```

systemctl restart nginx
```
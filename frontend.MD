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




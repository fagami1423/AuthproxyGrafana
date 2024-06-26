### Grafana Proxy Authentication for automatic login
This project is designed to provide a seamless user experience by implementing proxy authentication for Grafana, enabling automatic login for users.

### Overview
Grafana is a popular open-source platform used for monitoring and visualizing metrics from a wide variety of data sources. However, it requires users to manually log in to access the dashboards, which can be inconvenient in some scenarios.

This project aims to overcome this limitation by implementing a proxy authentication mechanism. With this setup, the proxy server performs the authentication and passes the authenticated user's information to Grafana. As a result, users are automatically logged into Grafana, bypassing the need for manual login.

### Features
Automatic login to Grafana via proxy authentication
Improved user experience by eliminating the need for manual logins

### Grafana configuration
* grafana.ini
```
[users]
allow_sign_up = false
auto_assign_org = true
auto_assign_org_role = Editor

[auth.proxy]
enabled = true
header_name = X-WEBAUTH-USER
header_property = username
auto_sign_up = true
```

### Run the project

```
docker compose up -d 
```
* it runs in 
* `http://localhost:3000`

* but for the auto login use, the username and password are in htpasswd file.
* `http://username:password@localhost:3000`

This works but it is vunerable in security. Though users won't be able see on the browser, it is still unsafe with this method.

you can use your own port 

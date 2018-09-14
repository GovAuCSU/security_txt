This is our current solution to allow access to `.well-known` folder using deprecated feature from Static-buildpack. In the future, we need to migrate to nginx-buildpack when it is added to cloudfoundry. 

### HOW TO:

Move all the files you need for `.well-known` into "./site/.well-known"

Push the app and map `subdomain.example.com/.well-known`  to this app using the following command:

```
cf push securitytxt -d example.com --hostname subdomain --route-path ".well-known"  
```



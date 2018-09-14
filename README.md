This is our current solution to allow access to `.well-known` folder using deprecated feature from Static-buildpack. In the future, we need to migrate to nginx-buildpack when it is added to cloudfoundry. 

### HOW TO:

Move all the files you need for `.well-known` into "./site/.well-known"

Push the app and map `subdomain.example.com/.well-known`  to this app using the following command:

```
cf push securitytxt -d example.com --hostname subdomain --route-path ".well-known"  
```

__OPTIONAL:__

You can also modify `manifest.yml` to add the route in there instead of using arguments in `cf push` command. 
This is useful for when you want to map this same app to multiple `/.well-known` routes for multiple subdomains
Note that when you add route option into manifest.yml, you can no longer adding route using `cf push` command arguments.



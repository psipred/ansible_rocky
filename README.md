
# New Repository for deploying webserver on Rocky

Hopefully this will be a new and united ansible for both our production and staging web environments. And we can stop maintaining 2 repos. 

## Installing on staging


1.  Do not forget to add your ssh credentials to the machines!



``` bash
> ansible-playbook -i staging_hosts --extra-vars "my_env=staging" deploy_staging.ym
```


## Notes on creating passwords with openssl

1. create a salt

``` bash
> openssl rand -base64 32
```

2. Then hash the password with the salt

```
> openssl passwd -6 -salt <salt> <password>
```
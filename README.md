
# New Repository for deploying webserver on Rocky

Hopefully this will be a new and united ansible for both our production and staging web environments. And we can stop maintaining 2 repos. 

## Installing on staging


1.  Do not forget to add your ssh credentials to the machines!



``` bash
> ansible-playbook -i staging_hosts --extra-vars "my_env=staging" deploy_staging.yml
```

## Installing on Prodcution

### TODO

Make sure to the blastmachine and software install roles send things to the right/same/consitent places
as the current setup and the staging setup

### Instructions

1.  Do not forget to add your ssh credentials to the machines!


``` bash
> ansible-playbook -i staging_hosts --extra-vars "my_env=production" deploy_staging.yml
```



## Notes on creating passwords with openssl

1. create a salt

``` bash
> openssl rand -base64 32
```

2. Then hash the password with the salt

```
> openssl passwd -1 -salt <salt> <password>
```

## Notes on /etc/sudoers

Fresh machines from TSG have a fixed sudoers file and changes will be lost at midnight each day. Email requests with any permenant changes you want to make to /etc/sudoer
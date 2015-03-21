# Docker Image for Vertica

Warning: This is very experimental. The level of testing has consisted of "Start server, run some sql, shutdown server, restart server, run some sql". What it does manage to do is get a vertica process up and running in a docker container. For the purposes of testing applications with fig and such, this might be sufficient, but don't let it anywhere near production.

The image creates a database called docker, with a blank dbadmin password.

Base OS is Ubuntu 14.04.

## Usage:

Download the Vertica DEB package from https://my.vertica.com and put it in this folder as "vertica.deb".
Then run:
```bash
docker build -t sumitchawla/vertica .
```

### To run without a persistent datastore
```bash
docker run -p 5433:5433  sumitchawla/vertica
```

### To run with a persistent datastore
```bash
docker run -p 5433:5433 -d -v /path/to/vertica_data:/home/dbadmin/docker sumitchawla/vertica
```
### Connection Parameters
 Default DB Name - docker
 
 Default User - dbadmin
 
 Default Password (NO PASSWORD) - 

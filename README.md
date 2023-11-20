# LMS CONFIG

## Prerequisites
- Docker
- git

## First run
1. Clone the repo to a directory
2. Copy LMS to lms directory, it should be places next to the `lms-config` directory
```
    /TheApp
        /lms-config
            /docker
            /config
        /lms
            ...lms files
```
3. Go to `lms-config/docker` directory and run:
```
docker compose up -d
```
4. Run:
```
docker exec -it lms sh 
```
5. Make sure that you are in `/var/www/html` directory (`pwd` command)
6. Run `composer install`
7. Open a browser and go to `localhost:1234` 
8. Copy the `chown` and `chmod` commands from the page that has opened and paste it into the container (if you already exited the container run `docker exec -it lms sh` again)
9. Refresh the page twice (first time it will migrate the DB and for the second time it will open the setup manager)
10. You can now make changes in files from `/lms` directory

## Database
If you want to check what's inside the DB, go to `localhost:8085`, the email address is `admin@admin.com` and password is `admin`

### First run
1. After login right click on `Servers` in the sidebar on the left hand side, then `Register -> Server...`
2. Provide a name (could be anything)
3. Go to the `Connection` tab
4. For `Host name/address` enter `postgres`
5. Port leave as is
6. Enter `lms` in `Maintenance database` input
7. Set `Username` and `Password` to `admin`
8. Save



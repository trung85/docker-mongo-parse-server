

## Google Project: delivery-tracker-1523842970758


## APNS and GCM for Push Notifications
You may want to send Push Notifications with the Parse server, you must configure GCM and APNS.
> NOTE: don't forget to add the ***.p12*** certificate to your `parse-server` container, needed for Apple Push Notifications. You can modify the `parse-server/Dockerfile`:
```
...

ADD ./path-to-certificate.p12 ${PARSE_HOME}
...
```


## First run

    $ git clone https://git@github.com:trung85/docker-mongo-parse-server.git mongo-parse-server
    $ cd mongo-parse-server
    $ docker-compose up # add -d for `demon` mode

## Build (if you make changes within the `Dockerfile`s)

    $ docker-compose build

## Test Parse Server

```
POST
curl -X POST \
-H "X-Parse-Application-Id: ADXUM1FFKTHI9RMOEKUXUOAGU7RJIY" \
-H "Content-Type: application/json" \
-d '{"score":1337,"playerName":"Sean Plott","cheatMode":false}' \
http://localhost:1337/parse/classes/GameScore

GET
curl -X GET \
-H "X-Parse-Application-Id: ADXUM1FFKTHI9RMOEKUXUOAGU7RJIY" \
-H "Content-Type: application/json" \
-d '{}' \
http://localhost:1337/parse/classes/GameScore

```

## Install brew

```
$ gcc --version
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew doctor
$ brew update
```
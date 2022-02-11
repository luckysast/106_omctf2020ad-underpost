## Docker

### Build Image

Run `docker-compose build` from the project's root.

### Run Checker Service in Docker container locally

Run `docker-compose up` from the project's root.

### Swagger

Available at: `http://<serverip>:3001/api/`.

### UI

Available at: http://<serverip>:3080

### Preparation

To correct work, the following entities must be created using Admin account:
* several shelters where from/to goods are delivered  (bunkers)
* several porters accounts who deliver goods (couriers). Start position of porter must be the same as any shelter coordinates
* several goods. Each good is produced in only one shelter. Shelter can produce several good. Images for goods should be prepopulated in the /images folder in the container


It can be done using admin account or you can use prepopulated SQLite database.

Pre-populated myDb file should be placed into /init folder and ENV variable 'INIT' must be set to 'yes' or 'cond' before docker image build (docker-compose or docker).


### Notes

If you run `underpost-api` service using docker-compose, the `host` parameter for checker will be `192.168.50.3:8079` when checker up on the same server and belongs underpostnet network.
Otherwise use <serverip>:3001
IP can be changed in `underpost-api`'s docker-compose `ipv4_address` section.
Port can be changed in `underpost-api`'s Dockerfile `EXPOSE` section.


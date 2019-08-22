1. **docker network create --driver overlay frontend** - create new network
2. **docker network create --driver overlay backend** - create backend network
3. **docker service create --name vote -p 80:80 --network frontend --replicas 2 dockersamples/examplevotingapp_vote:before** - create vote service
4. **docker service create --name redis --network frontend redis:3.2** - create redis service
5. **docker service create --name worker --network frontend --network backend dockersamples/examplevotingapp_worker** - create worker service
6. **docker service create --name db --network backend --mount type=volume,source=db-data,target=/var/lib/postgresql/data -d postgres:9.4** - create postgres service
7. **docker service create --name result -p 5001:80 --network backend -d dockersamples/examplevotingapp_result:before** - create result service


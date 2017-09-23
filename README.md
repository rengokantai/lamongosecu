# lamongosecu
```
db.createUser(
{
user:'',
pwd:'',
roles:[
  {
    role:readWrite',
    db:'name'
  }

]

}
)
```


```
mongod --dbpath /data/db --logpath /data/db/mongo.log -- fork ---auditDestination syslog
```




### Enabling auditAuthorizationSuccess
config.yaml
```
systemLog:
  destination: file
  path: /data/db/mongo.log
storage:
  dbPath: /data/db
auditLog:
  destination: file
  format: JSON
  path: /data/db/auditLog.json
setParameter: { auditAuthorizationSuccess: true }
```
```
mongod --config config.yaml --fork
```
test
```
use dbname
db.coll.insert({})
```

### Security checklists
```
bind_ip
```
```
mongod --noscripting
```


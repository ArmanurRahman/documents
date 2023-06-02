# Insert

If duplicate id appears in insetMany query. By default duplication error will occurs and rest of the documents will not be inserted. inserted documents before the error will not __rollback__.

 *To continue the insertion we need to set ordered option as true*

```js
db.company.insertMany([{_id: 'Apple', type: 'IT'}, {_id: 'Tesla', type: 'Automobile'}, {_id: 'google', type: 'IT'} ], {ordered: false})
```

## Write Concern

write concern is after execute insert query, it will wait for confirmation of response. By default the writeConcern is true. if writeConcern is false, mongo will response back without confirmation.

```js
db.company.insertOne({_id: 'Meta', type: 'SNS'}, {writeConcern: {w: 1, j: true}})
```

## Bulk import

```sh
mongoimport tv-shows.json -d movieData -c movies --jsonArray
```

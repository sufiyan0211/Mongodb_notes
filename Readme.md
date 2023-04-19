# MongoDB

## Installation commands
1. ```brew update```
2. ```brew tap mongodb/brew```
3. ```brew install mongodb-community@6.0```

## Running MongoDB
1. To <b>run</b> MongoDB (i.e. the mongod process) <b>as a macOS service</b>, run:<br>
    ```brew services start mongodb-community@6.0```<br>
   To <b>stop</b> a mongod running as a macOS service, use the following command as needed:<br>
   ```brew services stop mongodb-community@6.0```<br>
2. To run MongoDB (i.e. the mongod process) <b>manually as a background process</b>, run:
    * For macOS running Intel processors: <br>
        ```mongod --config /usr/local/etc/mongod.conf --fork```<br>
    * For macOS running on Apple Silicon processors:<br>
        ```mongod --config /opt/homebrew/etc/mongod.conf --fork```<br>
    * To <b>stop</b> a <b>mongod</b> running as a <b>background process</b>, connect to the <b>mongod</b> using <b>mongosh</b>, and issue the <b>shutdown</b> command as needed.


## Database Commands

### Database Commands
1. <b>View</b> all databases<br>
    ```show dbs```
2. <b>Create</b> a new or <b>switch</b> databases<br>
    ```use dbName```
3. View current Database<br>
    ```db```
4. Delete database<br>
    ```db.dropDatabase()```


### Collection Commands
1. Show collections<br>
    ```show collections```
2. Create a collection named as <b>myCollection</b><br>
    ```db.createCollection('myCollection')```
3. Drop a collection named as <b>myCollection</b><br>
    ```db.myCollection.drop()```


### Data Commands
1. Insert one entry in a collection<br>
    <pre>
    db.myCollection.insertOne({
        field: value,
        ...
        field: value
    })
    </pre>

2. Insert more than one entries in a collection</br>
    <pre>
    db.myCollection.insertMany([
        {
            field: value,
            ...
            field: value
        },
        {
            field: value,
            ...
            field: value
        },
        ...
        {
            field: value,
            ...
            field: value
        }
    ])
    </pre>
3. Show all rows in a collection</br>
    <pre>
    db.myCollection.find()
    </pre>
4. Show all rows in a collection [in a pretified format]</br>
    <pre>
    db.myCollection.find().pretty()
    </pre>
5. Show <b>upto 5</b> rows in a collection</br>
    <pre>
    db.myCollection.find().limit(5)
    </pre>
6. Find row/rows</br>
    <pre>
    db.myCollection.find({name: 'Myname'})
    </pre>
7. <b>Count</b> the rows in Output</br>
    <pre>
    db.myCollection.find({name: 'Myname'}).count()
    </pre>
8. Find the first row matching the output</br>
    <pre>
    db.myCollection.findOne({name: 'Myname'})
    </pre>
9. Sort the result</br>
    <pre>
    db.myCollection.find().sort({field:-1});
    </pre>

    field: -1 --> sort in decreasing order </br>
    field: 1  --> sort in increasing order </br>
10. Update the row
    * Update one row only</br>
        This will update only one row.</br>
        <pre>
        db.myCollection.updateOne({language: 'Java'}, { $set:{memberSince: 8} } );
        </pre>
    * Update many rows</br>
        This will update one or more than one rows.</br>
        <pre>
        db.myCollection.updateMany({language: 'Java'}, { $set:{memberSince: 8} } );
        </pre>
    $set: {field: newValue} --> set the value </br>
    $inc: {field: newValue} --> increment the value by newValue </br>
    </br>
    * Update the row when there is no matching
        <pre>
        db.myCollection.updateMany( {language: 'C#'}, { $set:{name: "Rakesh"} }, {upsert: true} );
        </pre>


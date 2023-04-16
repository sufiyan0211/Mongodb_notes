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

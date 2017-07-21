
# Media server for group call with recording audio/video based on Kurento Media Server (KMS)

### KMS Installation
```
echo "deb http://ubuntu.kurento.org trusty kms6" | sudo tee /etc/apt/sources.list.d/kurento.list
wget -O - http://ubuntu.kurento.org/kurento.gpg.key | sudo apt-key add -
sudo apt-get update
sudo apt-get install kurento-media-server-6.0
```

### Required

Node Version: Node 8.x
### Install application
```
npm install bower -g
npm install
cd server/static
bower install
```

### Run
```
node index.js
```
### Server configure
```
./server/index.js 

const argv = minimst(process.argv.slice(2), {
    default: {
        as_uri: 'https://localhost:8443',
        ws_uri: 'ws://127.0.0.1:8433/kurento'   // your KMS uri
    }
});

## Troubleshooting
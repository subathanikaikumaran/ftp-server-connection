# ftp-server-connection
The way to access server to local and local to server in your vscode. 

<b>1.</b> Create a new folder .vscode

<b>2.</b> Create a json file sftp.json

<b>3.</b> Add configration.

##### Case 01

If you need to access the server with domain address, Add the below json body into your sftp.json file
```json
{
    "name": "My Server",
    "host": "www.domain.lk",
    "protocol": "ftp",
    "port": 21,
    "username": "username",
    "remotePath": "/your project path",
    "uploadOnSave": true,
    "password": "password"
    
} 
```


##### Case 02

If you need to access the server with internal IP address, Add the below json body into your sftp.json file

```json
{
    "name": "Project Name",
    "profiles": {
        "cloud": {
            "context": "cloud",
            "name": "Server",
            "host": "Your IP",
            "protocol": "sftp",
            "port": 22,
            "username": "username",
            "password": "password",
            "remotePath": "/var/www/html/project folder",
            "uploadOnSave": true
        }
    },
    "defaultProfile": "cloud"
} 
```

##### Description

- `protocol` - `sftp`/`ftp`
- `port` - The port number - `22`/`21`/any other
- `remotePath` - The project path - `public_html` OR `/var/www/html/project folder`
- `uploadOnSave` - `true` - It will upload and download the new changes files from local and server, If you set `false` it will stop the process.

Once you edit your json file, you will able to upload and download the files from the server to local.
eg: `sync.remoteToLocal`


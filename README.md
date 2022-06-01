# Fluree Setup Readme

A documentation to setup a decentralized ledger using [Fluree]('https://flur.ee/)

### As part of Advanced Blockchain Technology Assignment

Author: _Ramdhani Rachmansyah_  
George Brown College

---

## Install Fluree

There are ways to install Fluree:

### 1. Using Docker

`docker run -d --restart=always -p 8090:8090 fluree/ledger:latest`

### 2. Download Fluree

- Install Java 11 or above
- [Download latest version]('https://s3.amazonaws.com/fluree-releases-public/fluree-stable.zip)
- Run `./fluree_start.sh`

> Installing via HomeBrew is not working. The Brew Tap is broken

### Open Admin UI on `http://localhost:8090`

## Transaction

### Create Ledger

On the Admin UI, click **Add Ledger**

> Ledger name: use lowercase or kebab-case only

### Create Schema

Schema is created by adding Collections

- Go to `Transact` menu
- On the Transaction box, input:

```
[
  {
    "_id": "_collection",
    "name": "person"
  },
  {
    "_id": "_collection",
    "name": "chat"
  }
]
```

- Click play button on the top right side

## Add data

- On `Transact` menu, input:

```
[
  {
    "_id": "person",
    "handle": "oRamirez",
    "fullName": "Oscar Ramirez"
  },
  {
    "_id": "person",
    "handle": "cStuart",
    "fullName": "Chana Stuart"
  }
]
```

## Update data

- On `Transact` menu, input:

```
[
  {
    "_id": ["person/handle", "dsanchez"],
    "age": 71
  }
]
```

## Delete data

- On `Transact` menu, input:

```
[
  {
    "_id": ["person/handle", "zsmith"],
    "_action": "delete"
  }
]
```

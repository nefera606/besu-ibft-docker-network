NODE1: BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=
NODE2: qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM=
NODE3: zNHKczHZ05W4fPALZMl5G4DuIGVbTxtfp86PQDIklhA=

## PRIVACY GROUP ##
curl -X POST http://127.0.0.1:8881/findPrivacyGroup \
  -H 'Content-Type: application/json' \
  -d '{
    "addresses": [ 
      "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=", 
      "qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM=" 
    ]
}'

curl -X POST http://127.0.0.1:8881/createPrivacyGroup \
  -H 'Content-Type: application/json' \
  -d '{ 
    "addresses": [ 
      "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=", 
      "zNHKczHZ05W4fPALZMl5G4DuIGVbTxtfp86PQDIklhA" 
    ], 
    "from": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=", 
   "name": "Organisation A", 
   "description": "Contains members of Organisation A" 
 }'

## SEND & RECEIVE ##
curl -X POST \
http://localhost:8881/send \
-H 'Content-Type: application/json' \
-d '{ 
      "payload": "SGVsbG8sIFdvcmxkIQ==",
      "from": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=",
      "to": ["qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM="]
    }'

curl -X POST \
http://localhost:8882/receive \
-H 'Content-Type: application/json' \
-d '{
      "key": "Ab/z67VbVu8WXYFS4uezuIOMJishp693mrxIEgTMQSQ=",
      "to": "qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM="
    }'

curl -X POST \
http://localhost:8881/send \
-H 'Content-Type: application/json' \
-d '{ 
      "payload": "SGVsbG8sIFdvcmxkIQ==",
      "from": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=",
      "to": ["BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY="]
    }'

curl -X POST \
http://localhost:8881/receive \
-H 'Content-Type: application/json' \
-d '{
      "key": "GgP8miRw32OCQvdEr8Smw0tXK/+aoj2bQP156dCCTrY=",
      "to": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY="
    }'



curl -X POST \
http://localhost:8881/send \
-H 'Content-Type: application/json' \
-d '{ 
      "payload": "SGVsbG8sIFdvcmxkIQ==",
      "from": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=",
      "privacyGroupId": "GCh+2iOJQekumSVu8JgsjN7h9zXbPR66vsUVtQnvGlw="
    }'
curl -X POST \
  http://127.0.0.1:8881/receive \
  -H 'Content-Type: application/vnd.orion.v1+json' \
  -d '{
    "key": "pIvP5kJr5cWOifiPqTlMxm8xVqXmVIpfEFe/+Vyawgk=",
    "to": "GCh+2iOJQekumSVu8JgsjN7h9zXbPR66vsUVtQnvGlw="
}'


curl -X POST \
http://localhost:8881/send \
-H 'Content-Type: application/json' \
-d '{ 
      "payload": "SGVsbG8sIFdvcmxkIQ==",
      "from": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=",
      "to": ["qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM="]
    }'
   {
     from: web3.eth.accounts[0], 
     data: '0x608060405234801561001057600080fd5b5060c68061001f6000396000f30060806040526004361060485763ffffffff7c01000000000000000000000000000000000000000000000000000000006000350416630c55699c8114604d5780631a15863d146072575b600080fd5b348015605857600080fd5b50605f6089565b6040805191825251602090910181900390f35b348015607d57600080fd5b506087600435608f565b005b60005481565b6000805490910190555600a165627a7a72305820b6f261f7030cfb0264b28c3ad4f4fdaa20f01d576265078b31f8154bc162ec180029', 
     gas: '4700000'
   }

curl -X POST \
--data '{
    "jsonrpc":"2.0",
    "method":"eea_sendTransaction",
    "params":[{
        "from": "0x982cdba86ad9267681935e572bd8f076e18fd57a",
        "data": "0x608060405234801561001057600080fd5b5060c68061001f6000396000f30060806040526004361060485763ffffffff7c01000000000000000000000000000000000000000000000000000000006000350416630c55699c8114604d5780631a15863d146072575b600080fd5b348015605857600080fd5b50605f6089565b6040805191825251602090910181900390f35b348015607d57600080fd5b506087600435608f565b005b60005481565b6000805490910190555600a165627a7a72305820b6f261f7030cfb0264b28c3ad4f4fdaa20f01d576265078b31f8154bc162ec180029",
        "privateFrom": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=","privateFor": ["GCh+2iOJQekumSVu8JgsjN7h9zXbPR66vsUVtQnvGlw="],"restriction": "restricted"}], 
        "id":1}' \
        http://127.0.0.1:8551

curl -X POST \
--data '{
    "jsonrpc":"2.0",
    "method":"eth_sendTransaction",
    "params":[{
        "from": "0x982cdba86ad9267681935e572bd8f076e18fd57a",
        "data": "0x608060405234801561001057600080fd5b5060c68061001f6000396000f30060806040526004361060485763ffffffff7c01000000000000000000000000000000000000000000000000000000006000350416630c55699c8114604d5780631a15863d146072575b600080fd5b348015605857600080fd5b50605f6089565b6040805191825251602090910181900390f35b348015607d57600080fd5b506087600435608f565b005b60005481565b6000805490910190555600a165627a7a72305820b6f261f7030cfb0264b28c3ad4f4fdaa20f01d576265078b31f8154bc162ec180029",
    }]
        "id":1}' \
        http://127.0.0.1:8551

        "gasLimit": "0x76000",
        "gasPrice": "0x0",
        "value": "0x0",
        "to":"0x0"

curl -X POST --data '{"jsonrpc":"2.0","method":"eth_sendTransaction","params":[{"from": "0x982cdba86ad9267681935e572bd8f076e18fd57a","data": "0x608060405234801561001057600080fd5b5060c68061001f6000396000f30060806040526004361060485763ffffffff7c01000000000000000000000000000000000000000000000000000000006000350416630c55699c8114604d5780631a15863d146072575b600080fd5b348015605857600080fd5b50605f6089565b6040805191825251602090910181900390f35b348015607d57600080fd5b506087600435608f565b005b60005481565b6000805490910190555600a165627a7a72305820b6f261f7030cfb0264b28c3ad4f4fdaa20f01d576265078b31f8154bc162ec180029","gas": "0x27600","gasPrice": "0x0","value": "0x0","privateFrom": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=","privateFor": ["qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM="],"restriction": "restricted"}], "id":1}' http://127.0.0.1:8551
curl -X POST --data '{"jsonrpc":"2.0","method":"eea_sendTransaction","params":[{"from": "0x982cdba86ad9267681935e572bd8f076e18fd57a","nonce":"0x0","data": "0x608060405234801561001057600080fd5b5060c68061001f6000396000f30060806040526004361060485763ffffffff7c01000000000000000000000000000000000000000000000000000000006000350416630c55699c8114604d5780631a15863d146072575b600080fd5b348015605857600080fd5b50605f6089565b6040805191825251602090910181900390f35b348015607d57600080fd5b506087600435608f565b005b60005481565b6000805490910190555600a165627a7a72305820b6f261f7030cfb0264b28c3ad4f4fdaa20f01d576265078b31f8154bc162ec180029","gas": "0x27600","gasPrice": "0x0","value": "0x0","privateFrom": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=","privateFor": ["I26sw+ZNtp8xdaDBUWycsX+iXyb8lOwT1RRhnQYHh0s="],"restriction": "restricted"}], "id":1}' http://127.0.0.1:8551


curl -X POST --data '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":51}' http://127.0.0.1:8551

curl -X POST --data '{"jsonrpc":"2.0","method":"eth_accounts","params":[],"id":1}' http://127.0.0.1:8551

curl -X POST --data '{"jsonrpc":"2.0","method":"eth_getTransactionCount","params":["0x982cdba86ad9267681935e572bd8f076e18fd57a","latest"],"id":1}' http://127.0.0.1:8551

curl -X POST --data '{"jsonrpc":"2.0","method":"priv_getTransactionCount","params":["0x982cdba86ad9267681935e572bd8f076e18fd57a", "I26sw+ZNtp8xdaDBUWycsX+iXyb8lOwT1RRhnQYHh0s="], "id":1}' http://127.0.0.1:8545

docker exec -it besu-node-1 curl -X GET http://172.16.1.51:8880/upcheck

curl -X POST --data '{"jsonrpc":"2.0","method":"eea_sendTransaction","params":[{"from": "0x982cdba86ad9267681935e572bd8f076e18fd57a","nonce":"0x1","data": "0x608060405234801561001057600080fd5b5060c68061001f6000396000f30060806040526004361060485763ffffffff7c01000000000000000000000000000000000000000000000000000000006000350416630c55699c8114604d5780631a15863d146072575b600080fd5b348015605857600080fd5b50605f6089565b6040805191825251602090910181900390f35b348015607d57600080fd5b506087600435608f565b005b60005481565b6000805490910190555600a165627a7a72305820b6f261f7030cfb0264b28c3ad4f4fdaa20f01d576265078b31f8154bc162ec180029","gas": "0x27600","gasPrice": "0x0","value": "0x0","privateFrom": "BDUuik7jnXyzuSA8yEHxoQDJ88UrcWBRwJEvsQngLwY=","privateFor": ["qR0+FmdJm1POHiueCvQx8qf9vjT7YoudMevkviQoBnM="],"restriction": "restricted"}], "id":1}' http://127.0.0.1:8551

curl -X POST --data '{"jsonrpc":"2.0","method":"priv_getTransactionReceipt","params":["0xf15be1964c81b69c3f408f64caad237d97aa848358b37608a4c584811de2212f"],"id":1}' http://127.0.0.1:8545

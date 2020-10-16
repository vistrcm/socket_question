# socket_question

The sample server and client app to demonstrate the question:

How to identify which host initiated TCP connection?

1. build:
```
make
```

2. start the server
```
./server
```

3. start the client (a lot of output)
```
./client
```

4. check netstat data ( in the example 1477789 - pid of the server, 1477794 - pid of the client):
```
# netstat -atunp | egrep "(1477789|1477794)"
tcp        0      5 127.0.0.1:1876          127.0.0.1:32882         ESTABLISHED 1477789/./server
tcp        0      0 127.0.0.1:32882         127.0.0.1:1876          ESTABLISHED 1477794/./client
#
```

How to figure out which endpoint initiated connection without looking to the source code or using the process's names?
# How EFS automatically scales when files are added or removed?

EFS uses NFS behind the scenes which makes it scalable.

**NFS (Network File System)** is a protocol that allows accessing files over the network similar to how we access files locally.

It has client-server architecture where there is a NFS Server and NFS Client
- NFS Server is where actual data is stored.
- NFS Client is the system which accesses the data from NFS Server. Example: EC2, laptop, etc. To access the NFS Server, client mounts shared directory from the server.

> NFS Client (mounts the shared directory from the server) -> NFS Server (actual data stored)

Behind the scenes, there are read and write operations over NFS Protocol which is usually TCP port 2049.

NFS maintains file permissions similar to UNIX. It can use file locking to avoid multiple clients overwrite files at once.

Old NFS versions didn’t track the connections, which makes them stateless, for example NFS v3. Newer NFS versions supports authentication, caching and session tracking, which makes these versions stateful, for example, NFS v4.

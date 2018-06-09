# steamcmd
DockerFile for steamcmd based on CentOS where glibc runs smoothly.

## Purpose
This DockerFile will build an image with the latest CentOS && the librarys needed for steamcmd.

When new version of CentOS comes in you should be able to create new container preserving the Servers.

For this to work we will need a Volume where the DedicatedServers will be downloaded configured and preserved across containers updates.

## Usage
This step will be required only one time and will create a Volume for the data needed to be Persisted (the server files and config)
```
docker volume create steamDedServ
```

Now we can use that volume and inject it in our container (or others if you want to test other steamcmd solutions)
```
docker run -it -v steamDedServ:/DedServ dolpsdw/steamcmd -e USER='steamuser' PASS='steampasswd'
```

When new version of CentOS you can upgrade deleting the container without the volume, and re runing it.

*Ensure that you install your the Dedicated servers in /DedServ folder or they will not persist in the volume.
```
force_install_dir /DedServ/csgo
```

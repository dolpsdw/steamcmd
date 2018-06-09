# steamcmd
DockerFile for steamcmd based on CentOS where glibc runs smoothly.

## Purpose
This DockerFile will build an image with the latest CentOS && the librarys needed for steamcmd.

When new version of CentOS comes in you should be able to create new image and container preserving the Servers.

For this to work we will need a Volume where the DedicatedServers will be downloaded configured and preserved across containers updates.

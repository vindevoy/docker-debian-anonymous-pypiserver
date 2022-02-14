# docker-debian-anonymous-pypiserver

Image for PYPISERVER with FULL ANONYMOUS access, based on Debian (slim)

## WARNING: NOT MEANT FOR PRODUCTION PURPOSES

Use only in development or on your local machine.  This image provides an easy way to get started fast with pypiserver.

## Example usage

docker run -t -p 8080:8080 -v ~/packages:/opt/packages  vindevoy/debian-anonymous-pypiserver:[VERSION]

## Version numbers

- The version numbers are synced with the version of pypiserver.  
- The version of Debian is the latest from the slim series at the moment of release


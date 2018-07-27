docker build -t myimage .

docker run -d -p8080:8080 myimage

docker tag sourceimage author/destimage

docker push auth/destimage
docker exec -it containername /bin/bash

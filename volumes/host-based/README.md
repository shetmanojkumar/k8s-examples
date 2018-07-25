# Create cache folder in dir /home/ubuntu in nodes
mkdir /home/ubuntu/cache

# Create pod container and mount volume with container
kubectl create -f hostpath-pod.yml

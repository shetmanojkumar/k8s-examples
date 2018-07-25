# Create cache folder in dir /home/ubuntu in nodes
mkdir /home/ubuntu/cache

# Mount EBS volume to container
kubectl create -f hostpath-pod.yml

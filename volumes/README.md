# Create EBS volume
aws ec2 create-volume --size 1 --region us-west-1 --availability-zone us-west-1a --volume-type gp2

# Mount EBS volume to container
kubectl create -f aws-persist.yml

kubectl create -f aws-persist-claim.yml

kubectl create -f aws-pod.yml

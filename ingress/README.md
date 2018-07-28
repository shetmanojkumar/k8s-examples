create a SSL certificate for foo.bar.com host:

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /tmp/tls.key -out /tmp/tls.crt -subj "/CN=foo.bar.com"

Now store the SSL certificate in a secret:

kubectl create secret tls foo-secret --key /tmp/tls.key --cert /tmp/tls.crt

run ingres file withtls.yml
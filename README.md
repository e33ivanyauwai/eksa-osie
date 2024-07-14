FROM nginx:alpine
COPY . /usr/share/nginx/html

docker build -t hkjc-eksa-demo:1.0 .
docker tag hkjc-eksa-demo:1.0 localhost:5000/xxx/hkjc-eksa-demo:1.0
docker push yyy

IN DEV JUMPHOST:

pwd should be in /home/ubuntu
cd helm
helm create hkjc-eksa-demo
(Change to nodeport)
helm install hkjc ./hkjc-eksa-demo
helm list
helm uninstall hkjc

k get svc |grep NodePort

Then in web browser, open the output link.

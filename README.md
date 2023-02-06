# kubernetes-notes

File: update-containerd.sh

I took the Getting Started with Kubernetes, 3rd Edition OReilly live lesson
and it was very informative. However I did have a bug when in lession 10.4
when trying to setup my on-prem kubernetes cluster.

It seems the containerd is not a good fit for the kubeadm init command.

After searching the web, I did find some code that fixes that.


File: add-calico.sh

This is the command he typed in to add the calico networking plugin.


Install metrics deployment:

   kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

11.3 - Install ingress:

   Go to https://gitbhub.com/helm/helm, release, latest and download the latest .tar.gz for your platform
`
   tar xzf <tarball>
   sudo cp linux-amd64/helm /usr/local/bin
   helm upgrade --install ingress-nginx ingress-nginx --repo https://kubernetes.github.io/ingress-nginx --namespace ingress-nginx --create-namespace 

   k get pods -n ingress-nginx 

   k create deployment nginxsvc --image nginx --port 80

   k expose deploy nginxsvc

   k edit svc nginxsvc
     change ClusterIP to NodePort

   k create ingress nginxsvc --class nginx --rule 'nginxsvc.info/*=nginxsvc:80'
      then press Ctrl-Z, and enter bg to put it in the background

   add this to the end of /etc/hosts:
   # added this for port-forwarding (run in the background)
   127.0.0.1	nginxsvc.info

   then curl to out nginx server with:

   curl nginxsvc.info:8080
`

   

# kubernetes-notes

File: update-containerd.sh

I took the Getting Started with Kubernetes, 3rd Edition OReilly live lesson
and it was very informative. However I did have a bug when in lession 10.4
when trying to setup my on-prem kubernetes cluster.

It seems the containerd is not a good fit for the kubeadm init command.

After searching the web, I did find some code that fixes that.


File: add-calico.sh

This is the command he typed in to add the calico networking plugin.

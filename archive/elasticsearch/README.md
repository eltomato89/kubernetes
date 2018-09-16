I have _heavily_ cribbed this config from https://github.com/pires/kubernetes-elasticsearch-cluster, and I'm using his docker images. 

I've diverged enough from his configurations in a way that I decided to just pull them into this repository instead of trying to maintain a fork that won't ever get merged upstream. The largest change is I'm running the master nodes as a StatefulSet, _and_ having them act as ingest nodes. I've also added a NodePort service, for each master node. This helps for configuring clients to connect to the collection of nodes. I also put all the config into an `elasticsearch` namespace. 
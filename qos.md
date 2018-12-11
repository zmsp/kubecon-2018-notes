# Getting The Most Out Of Kubernetes with Resource Limits and Load Testing - Harrison Harnisch, Buffer

* Tools used for load Testing
   - loader.io
   - kubescope
* scaling Tools
   - prometheus
   - azure metrics
   - horizontal pod scaling
   - vertical pod autoscaler (vpa)
   - datadog
   - kubescope cli

* QOS: BestEffort
* QOS: burst effect: upper bound (limit), lower bound (request). Together Creates a bursty effect.
* QoS: class of Guaranteed
* QOS covered here https://kubernetes.io/docs/tasks/configure-pod-container/quality-service-pod/

* Over allocation tricky: becomes a problem when scaling up replica. Effect multiplier by replica number.
* Ideal resource allocation: little over allocation. NO under allocation.
* PSA: Heapster is deprecated, use prometheus
* Kubernetes Monitoring: How does it apply limit/request? Via cAdvisor. Connects to docker socket.

* Setting limits/requests ... https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/
* Testing strategy:
    - traffic: Start from 0 traffic and up traffic until crashes. (loader.io, kubescope was used to test etcd)
    - duration: run the pod and see the consumed resources over time.
    - look into fail logs
* lesson learned:
    - keep a fail log

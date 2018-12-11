Lookup:
# helm hub
# harbor
# virtus
# nats
# grpc


Questions:



# limit vs requests
# limit = upper bound request lower bound. Together Creates a bursty effect.
QOS: BestEffort
QOS: burst
Over allocation tricky: becomes problem when scaling up replica. Effect multiplier by replica number.
Ideal: little over allocation and no under allocation.

Kubernetes Monitoring: How does it apply limit/request? Via cAdvisor. Connects to docker socket.

Part-B:-

Issue_no_1:- Failed to pull image "gcr.io/google-samples/microservices-demo/adservice:v0.3.1": rpc error: code = NotFound desc = failed to pull and unpack image "gcr.io/google-samples/microservices-demo/adservice:v0.3.1": failed to resolve reference "gcr.io/google-samples/microservices-demo/adservice:v0.3.1": gcr.io/google-samples/microservices-demo/adservice:v0.3.1: not found
Solution:- Changing Image name can be solve this issue.

Issue_no_2:- Container server failed liveness probe, will be restarted in one of cartservice container.
Solution:- there was timeout issue in liveness prob hence we have increased the  initialDelaySeconds and periodSeconds value.

Issue_no_3:- 0/2 nodes are available: 1 node(s) didn't match Pod's node affinity, 1 node(s) had taint {node-role.kubernetes.io/master: }, that the pod didn't tolerate. found node affinity issue at redis pod
Solution:- wrong hostname was present in node affinity rule hence we updated it by qa-cluster-worker.

Part-C:-
Issue_no_1:- found connection issue at frontend-external service due to wrong port number avilable in frontent deployment configure. transport: Error while dialing dial tcp 10.96.8.118:8000: connect: connection refused"
Solution:- currencyservice had a wrong port configuration in environment variable. I just updated the port value
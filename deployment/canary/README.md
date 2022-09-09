
## Canary Deployment Strategy:
- Just like blue/green, a **canary** deployment strategy uses 2 environments.
- A portion of user base is directed to the new code in order to expose any issues before the changes are rolled out to everyone else.
- So we allow a small portion of our user base to use that new environment, and once we've confirmed that everything is working, **we roll out those changes to the main production environment as well**
- And then direct all of our users to that updated production environment.

### How are we making sure that we actually direct only a small portion of our traffic to this canary environment?
- Well, one kind of simplistic way to do that is through the number of replicas.
- So, in my main environment I had 3 replicas, and in my canary environment, I have only 1. 
- But my service is going to direct traffic to the pods in both environments. 
- So we have 3 Pods that are in the main environment, 1 in the canary environment, 
- And therefore, approximaely 1/4 of our traffic should be directed to this new canary environment, because it only has 1 replica while main environment has 3. 
- Of course, that's a very simplistic way to implement this canary structure, but just with the basic building blocks of Deployments in Kubernetes, it's an easy enough way for us to go agread and implement that for our purposes right now.

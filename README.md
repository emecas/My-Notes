My-Notes
========
How to build a distributed microservices architecture based on Sagas. I am following the book named Microservices Patterns.

https://livebook.manning.com/#!/book/microservice-patterns/chapter-4/v-8/89

There are two ways of building this saga architectures, choreography and orchestrated.
A choreagrapher is basically a central object able to talk with differents services allocated in differents containers.

An Orchestra is basically the abbility that every service have in order to talk with different services.

https://stackoverflow.com/questions/4127241/orchestration-vs-choreography

21 March 2018
Added an xml graph showing how a choreography saga object should work. 

A central object talking with differents services allocated in different docker containers. I think that this object should be based on Tram framework with any producer consumer paradigm, in this case, if i want to talk with serviceA, i have to push a command with the request within TopicA and retrieve the response from ServiceA. When i have that response, i can push another request to ServiceB and wait for the response, and so on, so forth. Doing this way, i can guarantee global consistency because, because if i do not receive the response in a proper time, i can send a command to the previous services in order to going back to previuos state.

https://github.com/eventuate-tram/eventuate-tram-sagas


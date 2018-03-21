My-Notes
========

Added an xml graph showing how a choreography saga object should work. 

A central object talking with differents services allocated in different docker containers. I think that this object should be based on Tram framework with any producer consumer paradigm, in this case, if i want to talk with serviceA, i have to push a command with the request within TopicA and retrieve the response from ServiceA. When i have that response, i can push another request to ServiceB and wait for the response, and so on, so forth. Doing this way, i can guarantee global consistency because, because if i do not receive the response in a proper time, i can send a command to the previous services in order to going back to previuos state.

https://github.com/eventuate-tram/eventuate-tram-sagas


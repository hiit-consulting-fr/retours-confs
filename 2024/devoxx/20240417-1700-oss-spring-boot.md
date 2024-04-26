# Meet with an OSS project: Spring Boot

## Main info
45' by Josh Long (Spring advocate) and Daniel Garnier-Moiroux

see the conference here:

TL;DR: 
Q/A about the spring ecosystem where the speakers shared resources, good practices and like in all Q/A answered question


## Notes

### GraalVM

resources:  
- book: Everything yuou never wanbted to know about Spring Boot AOT
- video: [Road to Spring](https://www.youtube.com/watch?v=TOfYlLjXufw)

Warning:  
- Be aware of spring profiles, using GraalVM the profile uised to build will also be used at runtime
- Java agents does not work well with GraalVM

### Spring-modulith

Today we find everywhere packages controllers/service/dao/repository where everything is public => BAD PRACTICE
Spring Modulith allows developers to build well-structured Spring Boot applications and guides developers in finding and working with application modules driven by the domain
find out more: https://spring.io/projects/spring-modulith

### Spring-events

Spring throws a lot of events (lkifetime events for example like applicationReady events)
We can easily listen and react to them or even emit custom events (interfaces ApplicationEvent and AppolicationEventPublisher)
Using events can be a good way to avoid making everything public.

We can even use annotations like @Externalise to publish directly to brokers (kafka, *Mq)

### Warning

In spring using the annotation @RerstController does not define a REST controller (in the sense that the defined controller does not have to follow REST architecture).
The good practice is to use the annotations @Controller et @ResponseBody

### Ressources to go further

Books:  
- Entreprise Innovation Patterns, Hphpe Woolf
- Rest in practice, Jim Webber
- Starbucks does not use two phase commit

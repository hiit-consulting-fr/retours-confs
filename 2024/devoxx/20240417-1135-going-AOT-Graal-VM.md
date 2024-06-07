# Going AOT - Everything you need to know about GraalVM

## Main info
45' by Alina Yurenko (Oracle)

see the conference here: https://www.youtube.com/watch?v=ukY9Kzu6sc0

TL;DR: 
What is AOT and why you should use GraalVM in your current java project. With a nice demo.

negatives:
- none, it was a great talk

## Some notes

What is GraalVM ?   
GraalVM is a jdk that can compile your java app into a native image (you target a specific OS and compiles an executable for this OS - no need for JVM anymore)

What is AOT ?   
AOT stands for Ahead Of Time. It means most of the work of processing/building/optimising your java app is made ahead of time.
It takes your app and analyses it, then compiles it to build a native app which is more performant, more secure and uses less resources. It also builds a lightweight app by analysing every bit of code your app uses and deletes all the rest from the final app.

Advantages? 
- Fast start: No JVM means no warmup before launching your app -> your app can launch in several ms !! It also is OS specific so you have to compile it again if you want to change OS
- Lower Resources Usage: Once again no JVM, only the resources your app uses => lighter
- Compact packaging: it deletes all the bits of code tou do not use in your app so lightweight app
- Security: less code means less surface of attacks 
Requirements:  
- java 21 or even better 22
- spring 3.3 (it has native image support - good time to migrate your project to this version)

Drawbacks
compilation takes a lot time, like a lot a lot. 

Still works with CI/CD, we can use GraalVM on certain env like production

Known Problems:  
- reflection: itis one oof the more challenging parts using reflection with graalVM because it happens at runtime. We can use config files rection-config.json to tell at compile time on which elements we are going to use reflection or use annotations (thanks to spring)
- some libraries are not supported (there is a github repo with al supported libraries 

What next ?   
- Layered native images. Compiles jdk, spring and other comon elements only one time and on change, we compile only new user code. It enables us to do less compilation AOT and drastically improve the compilation time. We can also share the common compilated resources across resources savoint time and resources

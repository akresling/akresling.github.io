---
layout: post
title: Mule, Yay or Nay?
date: 2016-1-4
---

#### What is Mule?
If you haven't heard of it I don't blame you, neither did I until this summer. Mule ESB "is a lightweight Java-based enterprise service bus (ESB) and integration platform that allows developers to connect applications together" ([www.mulesoft.com](https://www.mulesoft.com/resources/esb/what-mule-esb)). At least that's the description on the website, but what does all of that mean? In short, it is a tool that allows you to connect a variety different applications and services. The selling point is the "Anypoint Studio" IDE, built on top of Eclipse, which provides a graphical interface for building the system. You can simply drag and drop components to put together an API that connects to a database, maps the data, and sends it to another application. You can see an example of it below:

![](/images/mule_ex.png)
*An example of a simple Mule API path*

#### The GUI API Builder
The "drag and drop" development environment is ideal for making application connections quickly and reduce the deployment time. To accomplish this it has many different connectors, endpoints, and transformers available to drag onto your "board" which can be connected in order to build your flow of data. Additionally, if there is some transformer that does not come natively with Anypoint Studio there is a tool which you can use to download new connections. 

<div class="image_row">
<img src="/images/mule_comp1.png" class="inline"> 
<img src="/images/mule_comp2.png" class="inline"> 
<img src="/images/mule_endpoints.png" class="inline"> 
<img src="/images/mule_flow.png" class="inline"> 
<img src="/images/mule_transformers.png" class="inline">
<em>Some of the possible connectors that can be used to build the system</em>
</div>


So what if you can't find a connector that does exactly what you are looking for? Luckily, there are available connectors that let you write custom code to hook into the flow and do whatever you wish in them. This is where I ran into my main problem: even though the pre-made connectors can do a lot of things that you might need, their functionality is limited to their preset designs. When I started to use it more, I noticed I was often relying on this custom code connector to solve my problems. Due to the complex nature of the native connectors, I actually found it easier to write my own custom connector to do a specific task. This brought up another problem: since the process of making an API endpoint with the GUI builder is different from the traditional way of writing code, I found Mule to have quite a significant learning curve. 

![](/images/java_ex.png)
*An example of using a java component to insert java code to the route*

#### Should you use it?
That question can be answered by looking at couple of factors that influence the decision to use any specific software stack. Largely important are the initial requirements for the software. I would argue that the implementation stack is highly dependant on the design of the system, which is in turn dependant on the requirements. 

![](/images/Waterfall_model.png)
*Implementation stack is dependant on design and requirements (from http://www.umsl.edu/~hugheyd/is6840/images/Waterfall_model.png)*

In the case of Anypoint Studio you would want to see that the majority of your requirements can be fulfilled using the connectors provided by the tool rather than using a lot of custom written code. If you're using a significant amount of custom code, it may be simpler to write the application entirely in code using a preferred framework, instead of spending time trying to learn Mule. There is another important decision factor; availble team expertise with the tools used in the stack. If there is no one on the team who knows the tool, this can make implementing the software with the tool difficult or it may take more time in order to learn it.

My use of Mule brought with it a very interesting learning experience. Not only did I get a chance to learn this new tool and make a small system prototype with it, but I also got a chance to see the difficulties in introducing new technologies to a team's stack. Although we initially did the prototype in Mule, a later review of the requirements showed that Mule's strengths would not be effectively utilized. As well as the issue of a lack of team members skilled in the new tool, we did not continue to use the technology. Not to say Mule is a bad tool, but rather because it did not fit in the design of the system and the existing architecture. 

<br/>
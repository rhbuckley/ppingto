# pping.to

What is pping.to, you ask? It's a easy-to-use developer notification service. One of the challenges I encountered during my brief journey in the field of Computer Science was receiving notifications for specific tasks, which can be somewhat time-consuming. While we do have logging, it's important to note that logging can be likened to polling. With logging, we only become aware of issues when we actively check, whereas receiving notifications on your phone or in your inbox is an interrupt-driven process, providing timely updates.

## Current Progress

My current progress... Where I am at currently. Though I have created, tested, and implemented an MVP for the pping.to system, I have not been satisfied with my results. In my first design iteration I utilized Firebase, and Next.js to create a MVP, where a user is able to create an account, send notifications to a webhook, and receive those notifications on the intended device.

So, it worked, but what did I not really like. As I made my way through the design process, the biggest challenge for me has been the implementation of teams, or group-notifications. The reason why this has been such a challenge for me is deciding how to implement the sending of the notifications... do I propogate the notification to each individual in the team? Should I make separate team notification methods? (I decided to both propogate and allow for the subscribers of each channel to get the notifications)

### Iteration 1

I used Firebase, Firebase Auth & Next.js to create a MVP, however, at the end of the day, I was not happy with the result, as with my implementation of Firebase, I was unable to use the server-side rendering features of Next.js, as all of the authentication was handled through google and not my backend. As a result of this, I decided that I would implement the API myself, as not only would this give me a better understanding of creating a product, but this would also make my product more scalable in the future (is it going to grow that much? no, but I do wish to learn from this project). If anyone tells me you can use server-side rendering in firebase -- I know, I too found the solution of how to do it on the web.

### Iteration 2 (in progress)

For the API, I am using Go!, in combination with Gin and Gorm. The only thing that I am not too happy about with this iteration is that Gorm had a hell of a learning curve. In my models, I am using ENUMS to represent the state of the user's verification (did they verify their email? did they verify their phone number?), and the documentation on this issue is not quite clear, as different databases have different solutions tied to them (e.g. sqlite doesn't support enums, so the enums need to be implemented one way, postgres does support enums, but has a different implementation than mysql, etc).

I do not regret my choice however, as I am definitely learning a lot about creating a secure backend environment. I have currently finished the user and authentication parts of the project and am just putting the finishing touches on the channels, and integrations.

I am still up in the air about how I wish to do the updated web portion of the final product. I am leaning towards doing a refactoring of the current Next.js application and just adapting it, but I am also considering going back to Figma to sketch out some cleaner interfaces for the dashboard.


`Estimated Completion December 5th 2023`


#### Future Plans

Well, nothing is set in stone. When this project is done, I am going to try to gain some users to get some feedback. If the feedback is positive, I will continue adding other external integrations, however, we will see. 

-> Some (maybe) plans...
- Enable 2 way communication from Notification Method -> Program (like a telegram bot to interface with your program). 

---
title: From Wireframes to Data Structure
date: 2026-05-02
author: Libra Wu
summary: This week, we refined the wireframes for **Liminal** through more detailed offline discussion and clarified how each page should work. We also started turning the wireframes into a Data Definition Document by identifying the data behind user actions, such as creating an anonymous user/session, choosing or creating a room, selecting a room type, setting a background, and sending messages. After that, we began converting the DDD into an ERD to show the main data relationships between users, rooms, room types, messages, and reports. This helped us move from only thinking about the interface to understanding the system structure behind the website.

tags:
  - Wireframe
  - DDD
  - ERD
  - DataStructure
---
In this week’s progress, we focused on translating our wireframes into a clearer data structure for our anonymous chat website, Liminal. Previously, our work was mainly about the visual layout and user flow, such as the welcome page, the random room page, the create room page, and the chat page. However, this week we started to think more deeply about what happens behind the interface when a user interacts with the website.

We also had a more detailed offline discussion about the wireframes. During this discussion, we checked each page more carefully and clarified what each element meant. This helped us refine the structure of each page and make sure the interactions were easier to understand.

At first, I thought the Data Definition Document was only about listing the visible elements on the screen. For example, on the welcome page, I only considered the “Welcome” text and the “Start” button. However, after discussion and feedback, I realised that we also need to think about what happens after the user clicks the button. When a user clicks “Start”, the system may need to create a temporary anonymous user ID and a session ID. This helped me understand that the DDD is not just a description of the interface, but a way to define the data needed to support the user’s actions.

For the create room page, we also clarified the meaning of each wireframe element. The page name was only a label for ourselves, not a real page element shown to users. The annotations in the wireframe were used to explain the function of each box or button. Based on this, we identified important data such as room name, room type, background option, background colour, uploaded background image, and create button action. One important design decision was that users can either choose a solid colour background or upload an image as the room background. This means the database needs to record the background type as well as the related colour or image value.

After creating the DDD, we started to think about how to turn it into an ERD. This helped us separate interface elements from actual database entities. For example, buttons such as “Start” and “Create” are important in the user interface, but they do not usually become database tables. Instead, they trigger actions that create or update data. The main entities in our ERD include anonymous user, session, room, room type, room membership, message, and report. These entities help describe how users enter the website, create or join rooms, send messages, and report inappropriate content.

This process made our project feel more complete because we were no longer only designing how the website looks. We were also considering how the system works underneath. The DDD helped us list and explain the data, while the ERD helped us organise the data into relationships. For example, one room type can be used by many rooms, one room can contain many messages, and one anonymous user can send many messages. These relationships make the structure of Liminal clearer and more logical.

Overall, this week’s work helped us move from visual design to system thinking. By connecting the wireframes, DDD, and ERD, we gained a better understanding of how user actions are supported by data. The offline discussion also helped us refine the wireframe details and reduce misunderstanding within the group. This showed us that even a simple anonymous chat website needs both a clear interface and a clear data structure behind it. In the next stage, we can use this structure to support further development and make sure our website functions match the experience shown in our wireframes.
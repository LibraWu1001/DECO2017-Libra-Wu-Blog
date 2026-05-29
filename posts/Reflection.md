---
title: A3 Reflection
date: 2026-05-26
author: Libra Wu
---
## Evaluation of liminal

liminal is an anonymous chat room website made by our group. Users can browse rooms, create rooms, choose room backgrounds, randomly enter a room, and send text, images, and music in the chat. The idea comes from “liminal space”, which means a space that feels in-between, changing, and a little unreal. I wanted the website to feel less like a formal social platform and more like a soft, anonymous space where users can move between different conversations without fully showing who they are.

This reflection evaluates how well the final prototype works, what functions were completed, what problems still exist, and how the project could be improved.

## Technical Performance

Overall, the prototype can complete the main user flow. Users can enter from the Welcome page, go to the Room Selection page, browse room cards, use the floating “+” button, create a room, and enter the chat room. Compared with a static mockup, this project is more complete because users can actually interact with it.

We separated the main pages, including Welcome, Room Selection, Create Room, and Chat Room. This made the project easier to manage because each page has a clear purpose. For example, when we fixed the Create Room page, we could focus on the form, dropdowns, upload button, and CSS without changing the room card page too much.

The final project uses a Node.js backend and a SQLite database to store rooms and messages. This makes the prototype more stable because rooms and messages can stay after refreshing the page. However, the database is still local. If several devices connect to the same running server, such as on the same local network, they can see the same rooms and messages. But separate copies of the project will not sync by themselves. This helped me understand that having a database does not mean having a real shared online database.

The chat system currently uses API polling to update messages. This works for the prototype, but it is not the best way to make real-time chat because the browser keeps requesting messages repeatedly. If we continue developing this project, WebSocket would be a better choice. Media features also need more work because large files or slow external APIs may affect loading speed.

## User Experience

The user experience improved a lot during development. One of the biggest changes was the Room Selection page. A normal list would make the website feel like a basic tool instead of a social platform. So we changed it into a card-based layout inspired by Xiaohongshu and Pinterest. Each room has its own background and room name, which makes browsing more visual. It also helps show that each room is like a separate space users can enter.

The floating “+” button also makes the interface cleaner. Create and Random are not always shown on the page. They only appear after users click the “+” button. This reduces visual clutter and gives users different ways to enter the platform: choosing a room, creating a room, or randomly entering one.

The Create Room page became clearer after we separated Room Name and Room Type. Room Name is written by the user and appears on the room card. Room Type is selected from fixed options, including Gaming, Music, Reading, Movie, and Other. This is clearer than letting users type the room type freely.

For the visual style, we used a starry gradient background to make the website identity stronger. It is not a dark realistic night sky. Instead, it uses softer purple and blue colours with a dreamy feeling. This matches the name liminal better and makes the website feel calmer.

During development, the upload button, dropdowns, and input fields were not always visually consistent at first. Some elements used browser default styles, while others used custom CSS. Through repeated refinement, the final interface became more consistent across different pages, but this process showed me that a design system should be planned earlier. In the future, we should define standard button sizes, input heights, spacing, and label styles before building too many pages. Accessibility also needs more work, especially colour contrast, keyboard control, screen reader support, and responsive layout. Some icon buttons also rely on visual meaning, so future versions should include clearer labels or tooltips.

## Functional Requirements

The final prototype completed most core functions. Users can create rooms, save rooms into the SQLite database, enter rooms, send text messages, send image and music messages, choose room backgrounds, and delete the rooms they created. We also used external APIs, including Wikimedia Commons for online background image search and Jamendo for online music search.

After separating room name and room type, the room creation flow became clearer. Users can write a room name, choose a fixed room type, and select a background style. This gives users some freedom, but also keeps the system structured.

However, some functions are still at the prototype stage. Multi-user chat can work when users connect to the same backend server, but without public deployment, users on different networks cannot use the same shared system. GitHub can share our code, but it does not automatically run the backend or sync new database content.

Image and music functions also need improvement. Although media messages can be sent, future versions should include clearer previews, loading states, and error feedback. For example, if music search fails, the website should tell users what happened instead of making them think the button is broken.

## Testing Observations

As evidence for the evaluation, we tested the main user flow and several core features:

- Room creation test: A new room was created from the Create Room page, saved into SQLite, and still appeared on the Room Selection page after refreshing the browser.
- Room deletion test: The owner-based deletion function was tested by creating a room and deleting it from the same device. Rooms created by other users did not show the delete button.
- Messaging test: Text messages were sent inside a chat room, stored in the database, and loaded again after refreshing the page.
- Image message test: Image messages could be sent through the upload function, but larger files could affect loading speed.
- Online background test: Wikimedia Commons returned image results that users could select as room backgrounds.
- Online music test: Jamendo returned playable music results, but this feature depends on network connection and API availability.
- Multi-device test: Two devices on the same local network could access the same running backend and share room/message data. Devices on different networks would require deployment.

These tests showed that the main prototype flow worked, especially for room creation, room persistence, and basic messaging. They also showed the main technical limitations of the project: media handling depends on file size and API reliability, and real multi-network use requires deployment.

## Reflection and Future Improvements

One important thing I learned is that front-end design and backend logic cannot be planned separately. At first, it was easier to focus on page layout, buttons, and room cards. But a chat room website also depends on where rooms are stored, how messages are saved, and how different users see the same data.

Another thing I learned is that GitHub is not the same as deployment. GitHub can store and share code, but it does not automatically run the backend or update new user data. A real multi-user website needs a running backend service and a database that users can access.

I also learned that small UI details can affect the whole interface. Dropdown arrows, upload buttons, input alignment, and spacing may seem small, but if they are not consistent, the website can look less professional.

If we continue developing liminal, the first step should be deploying the backend online. The second step should be using WebSocket instead of polling, so the chat can feel more real-time. The third step should be improving media features, including image compression, music loading feedback, and error handling. We also need to do more accessibility testing.

Overall, liminal has developed from a wireframe into an interactive prototype with front-end, backend, and database support. It achieves the main flow of browsing rooms, creating rooms, and chatting. It also communicates the feeling of an anonymous, in-between online space. However, it is not a fully mature online chat product yet. The main areas for future improvement are deployment, real-time communication, media handling, and accessibility.

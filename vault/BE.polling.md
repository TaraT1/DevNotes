---
id: ae2x9ni537ohb1vwlolow6x
title: polling
desc: ''
updated: 1718123664970
created: 1718121565540
---
ref: https://javascript.info/long-polling
## Long Polling
Provides persistent connection with server that doesn't muse specific protocol like WebSocket or Server Sent Events. Simplest way and easy to implement.

## Regular Polling
- get new info from the server with periodic polling. Messages can be delayed between requests (10s). Even if there are no messages, server is bombed with requests every 10s. 

## Request-Response Cycle
Client request >>> API >>> server >>> client

Request response cycle
Client <------- >Server
-connection completes /terminates
- c.f.  WorkFile/Dendron/request response cycle
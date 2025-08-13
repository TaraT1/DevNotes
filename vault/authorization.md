---
id: eanu8rs76o2zowh9gglwibq
title: Authorization
desc: ''
updated: 1713462129924
created: 1713460027323
---
# Types of Authorization
- RBAC - Role Based Access Control
  - e.g. admin, editor, viewer roles. Used in admin panels, CMS tools
- ABAC - Attribute Based Access Control - access is based on user or resource attributes or contextual factors like time or location
  - ex: restrict access by dept, limit actions to certain hours
- ACL - Access Control Lists - each resource has its own list of permissions for users or groups
  - google drive file has its own ACL 

### Refs
- ref article: https://levelup.gitconnected.com/authentication-explained-when-to-use-basic-bearer-oauth2-jwt-sso-c3fb0aa083ef
- video https://youtu.be/9JPnN1Z_iSY

## Authentication vs Authorization
Authorization governs what the user has access to. Authentication makes sure user is who they say the are.

- An OAuth 2 application delegates the authentication to services that host a user account and asks for (limited) authorization from those services, after the user has given consent.  

## Multi-Provider Authorization
Reference: [Complete Guide to Multi-Provider OAuth 2 Authorization in Node.js](https://rrawat.com/blog/multi-provider-oauth2-nodejs) [github](https://github.com/Rishabh570/nodejs-social-auth-starter/tree/base)

## Models
Only single MongoDB doc can exist for a given email. (Email cannot be part of more than 1 account)
```javascript
//User model
const mongoose = require('mongoose')
const Schema = mongoose.Schema

//Schema to store info about other logged in accounts
const accountSchema = new Schema({
    name: String,
    userId: String,
    email: String
})

// create User Schema
var UserSchema = new Schema({
  name: String,
  connectedSocialAccounts: {//count of providers synced to logged-in acct
    type: Number,
    default: 1
  },
  otherAccounts: [accountSchema],// stores other accts user logged in from
  google: {
    accessToken: String,
    email: String,
    profileId: String,
  },
  github: {
    accessToken: String,
    email: String,
    profileId: String,
  },
  amazon: {
    accessToken: String,
    email: String,
    profileId: String,
  }
});

const User = mongoose.model('users', UserSchema);
module.exports = User;
```
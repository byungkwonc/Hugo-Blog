+++
title = 'Jarvis'
date = 2023-11-08T18:08:48+09:00
draft = false
+++

## J.A.R.V.I.S

### Client

- Slack Bot
- Create App
    + https://api.slack.com/apps/
- Settings > Basic Information
    + App Name : chatGptBot
    + App-Level Tokens
        + Token Name : AppToken (can change)
        + Scope : connections:write, authorizations:read,app_configurations:write
- Features > OAuth & Permissions
    + Redirect URLs : https://oauth.pstmn.io/v1/browser-callback
    + Scopes > Bot Token Scopes
        + app_mentions:read, channels:history, chat:write, chat:write.customize, groups:history, im:history, im:read, im:write, mpim:history
- Features > Event Subscriptions
    + Enable Events
        + Request URL : https://slackbot-chatgpt.vercel.app/slack
    + Subscribe to bot events
        + Event Name : app_mention
        + Required Scope : app_mentions:read
- Features > OAuth & Permissions
    + Install to Workspace
        + Bot User OAuth Token -> copy!. will use Server side
- Add to Slack Workspace App

### Server

- development
    - python, fastapi, openai, slack-sdk
    - local : `uvicorn app.main:app --reload`
- deploy
    - https://slackbot-chatgpt.vercel.app/
    - ![](/images/chatGptBot_Slack.png)
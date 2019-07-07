---
title: "National Hockey League API"
date: 2017-10-09
draft: false
---
As a developer, and a hockey fan. I spend a lot of time thinking about how to combine two things I love. Recently I had a cool NHL related app idea I'd like to turn into a [Progressive Web App](https://en.wikipedia.org/wiki/Progressive_web_app). The first step was finding a way to get the NHL related data I needed for the app. I needed an API.

If you do a quick web search for an NHL API, you'll likely find a few random Reddit threads linking to abandoned Github projects. Or you'll find a few companies out there that are willing to provide stats, for a fee. Usually a fee that's outside of the budget for a hobby app (read: free). 

If you keep digging you may come across reference to an official NHL API. This API has all the information you'd expect, is free, and is totally legit. The big drawback is that it's undocumented. You have to guess what the endpoints are to find your information.

Luckily there is some information out there. One blog post by [Kevin Sidwar](https://www.kevinsidwar.com/iot/2017/7/1/the-undocumented-nhl-stats-api) was particularly helpful: [The Undocumented NHL Stats API](https://www.kevinsidwar.com/iot/2017/7/1/the-undocumented-nhl-stats-api).

Here, Kevin has laid out some of the useful endpoints he's discovered. Things like how to find Teams, Players and even live game stats. I believe he's even been in contact with the team behind the API. From what I understand they know they'd like to document the API, but haven't got to it yet.

Kevin's project ([which you should check out here](https://www.youtube.com/watch?v=9eprFg7XjTQ)) involves player stats. Where my project will be more focused on the Teams, their upcoming games, and the outcome of those games. For this I'll likely rely on the **schedule** endpoint. 

The base URL of the API is [https://statsapi.web.nhl.com/api/v1](https://statsapi.web.nhl.com/api/v1). If you hit the 'schedule' endpoint you'll get a list of the games for today: [https://statsapi.web.nhl.com/api/v1/schedule](https://statsapi.web.nhl.com/api/v1/schedule).

If you're interested in getting more games you can also include a start and an end date. This link will provide you a schedule off all the games for the first week of the season: [https://statsapi.web.nhl.com/api/v1/schedule?startDate=2017-10-04&endDate=2017-10-11](https://statsapi.web.nhl.com/api/v1/schedule?startDate=2017-10-04&endDate=2017-10-11).

Another really useful endpoint I came across was the **standings** endpoint. Hit [https://statsapi.web.nhl.com/api/v1/standings](https://statsapi.web.nhl.com/api/v1/standings), and you'll get a nice set of data describing the current season's standings. Likely a super useful endpoint if you're building a sports app. 

One thing you may notice if you consume the API in your browser, is that the favicon is the [Major League Baseball](https://www.mlb.com/) logo. This is because the NHL works with [MLB Advanced Media (MLBAM)](https://en.wikipedia.org/wiki/MLB_Advanced_Media) to provide it's digital services.

I couldn't be more happy to discover this API. A lot of doubts about my project have cleared. Big thanks to Kevin for his work discovering those endpoints. I'm hoping the NHL API can help with more cool hockey related projects.

I'll write more about my new project soon.

Joe
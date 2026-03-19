# GraspSocial — Reddit API Integration

## About

GraspSocial (graspsocial.io) is an Instagram 
analytics and content intelligence platform 
for creators. This document describes how 
GraspSocial uses the Reddit API.

## How We Use the Reddit API

GraspSocial reads publicly available hot and 
rising posts from curated subreddits to 
identify trending topics within specific 
content niches such as fitness, wellness, 
business, and relationships.

This trending topic data is aggregated with 
signals from other sources including Google 
Trends and YouTube to surface content 
opportunities for creators before topics peak.

## What We Do

- Read public subreddit hot and rising posts
- Read post titles, scores, and comment counts
- Identify topic velocity over 24-48 hour windows
- Aggregate signals server-side for our platform

## What We Do Not Do

- Post, comment, vote, or interact in any subreddit
- Collect or store Reddit user data
- Access private or restricted content
- Operate under any Reddit username
- Build any experience within Reddit itself

## Authentication

Server-side only using application-only OAuth 
with client credentials. No Reddit user login 
or user data collection of any kind.

## Platform

https://www.graspsocial.io

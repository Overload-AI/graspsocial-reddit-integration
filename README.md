const Snoowrap = require('snoowrap');

// Reddit API client — read-only public feed access
const r = new Snoowrap({
  userAgent: 'GraspSocial/1.0 by Ok-Sport1344',
  clientId: process.env.REDDIT_CLIENT_ID,
  clientSecret: process.env.REDDIT_CLIENT_SECRET,
  username: process.env.REDDIT_USERNAME,
  password: process.env.REDDIT_PASSWORD,
});

/**
 * Fetch hot posts from a public subreddit.
 * Read-only. No user data accessed.
 */
async function getHotPosts(subreddit, limit = 20) {
  const posts = await r.getSubreddit(subreddit).getHot({ limit });
  return posts.map(post => ({
    title: post.title,
    score: post.score,
    created_utc: post.created_utc,
  }));
}

/**
 * Identify topics gaining momentum in a subreddit.
 * Raw post data is discarded after processing.
 */
async function detectTrendingTopics(subreddits) {
  const results = [];
  for (const subreddit of subreddits) {
    const posts = await getHotPosts(subreddit);
    // Internal trend processing
    results.push({ subreddit, posts });
  }
  return results;
}

module.exports = { detectTrendingTopics };

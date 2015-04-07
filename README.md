# AwSnap

[This link crashes Chrome](http://cortexture.net/chromebug/test.html)

At the time of publishing (April 5th, 2015) Chrome 41 seems to crash on long and/or malformed URLs. The crash only occurs when accessing the link through a webserver (i.e. using file:// will *not* crash).

As a proof of concept that this bug has the potential for abuse, [here is a reddit thread that crashes Chrome](http://www.reddit.com/r/webdev/comments/31kumu/this_post_crashes_chrome/) because of the content of a user-submitted post.  Crashing a thread via a comment [is also possible](http://www.reddit.com/r/test/comments/31ktcq/chrome_crash_demo_via_user_comment/).

#### Examples URLs that cause the crash:

`<a href="http://Lorem ipsum Culpa labore qui culpa enim nostrud eiusmod ullamco anim in dolor consequat voluptate in in laboris consequat dolor occaecat minim aliqua quis id in Duis eiusmod amet id do ex do dolore dolor anim sit deserunt do."></a>`

`<a href="http://xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.com"></a>`

#### Examples URLS that do not crash but look like they should:

`<a href="Lorem ipsum Culpa labore qui culpa enim nostrud eiusmod ullamco anim in dolor consequat voluptate in in laboris consequat dolor occaecat minim aliqua quis id in Duis eiusmod amet id do ex do dolore dolor anim sit deserunt do."></a>`

`<a href="http://xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"></a>`

### Updates:

###### April 5th, 2015 - 8:00pm

Confirmed bug in Chrome 41, 42, & 43 on MacOS and Windows in Browserstack.

###### April 5th, 2015 - 9:30pm

Confirmed bug in ~~Ubuntu and~~ Chrome OS

###### April 5th, 2015 - 10:00pm

Jumped the gun, mixed reports on Ubuntu

###### April 5th, 2015 - 10:05pm

Bug occurs on http:// only (https:// works fine)

###### April 6th, 2015 - 12:20am

Issue likely tracked down to [this bug](https://code.google.com/p/chromium/issues/detail?id=464270), fixed [here](https://codereview.chromium.org/1007323003).  Thanks to jgunsch for their [submission to HN](https://news.ycombinator.com/item?id=9326347).

###### April 6th, 2015 - 3:20am

"Aw, Snap!" is different than "He's Dead, Jim" errors in Chrome- I can't say for certain which were which at this point- I'm pretty sure most were 'Aw Snap' errors (hence the name).  See [proof](http://www.reddit.com/r/webdev/comments/31kumu/this_post_crashes_chrome/cq2r387), hopefully ;)

###### April 6th, 2015 - 9:00pm

Looks like the bug/fix linked above is correct, and the latest versions of 42/43 are actually not affected.  Which means this bug should be fixed when Chrome updates to 42.

The original reddit thread was [reposted to /r/bestof](http://www.reddit.com/r/bestof/comments/31n1ha/ujlblatt_creates_a_post_stating_this_post_crashes/) and almost made the front page before being removed by the admins (not surprised or offended by this, it was the right move).  I think that's the end of the story here.

* * *

Thanks to everyone who contributed to the discussion on this, especially [jgunsch](https://news.ycombinator.com/user?id=jgunsch) for showing up with the actual explanation.  And because they don't want any credit - thanks Katie and Oz!
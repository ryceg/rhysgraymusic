---
published: true
---
It's the classic move.

You're about to get your BMus, you're bright eyed and bushy tailed, and you then realise that you have no web presence.

Maybe you have a Facebook page, but the last thing you posted on that was back when you were in your last year of highschool, dreaming about winning all kinds of "Talented Young Person Is Talented And Young" prizes, getting featured in the local paper, and having to provide a link for the article.

So, you go and google "how to make a website", balk at the $12.99/month fee, then look at the "free web hosting" options, and then either make peace with the fact that Facebook will have to do just fine, or you'll get out your wallet, and start haemorrhaging money like that $12.99 wasn't going to go directly into your mouth (because you're an artist, remember? It's not like you were going to invest that money. You might have a nest egg, but that's all going to be subsidising your existence while you find your feet. Make peace with this bit while you have enough money to enjoy yourself).

This is the part where I tell you that you can have a professional looking website, for practically free, for next to no effort.

Only you can't.

This requires that you put in effort, and you'll have to pay a web domain registry fee if you want a custom domain (my website, [www.rhysgraymusic.com](www.rhysgraymusic.com) comes to the hefty tune of $18.99USD a year). Plus, let's be honest, unless you're a whiz at CSS, it will be a regular old website. But it's good enough for the job- the online presence of a musician is rather different to that of a web developer or game designer. There's no need for fancy animations, just 'About', 'Contact', 'Reviews', and maybe some links to your Facebook profile.

So, you have to weigh up your options- is it good enough? Am I cheap enough? Am I patient enough? $18.99USD? That's like, a whole game on Steam that's on sale. But that's it, though. No hosting costs. I spend more on pencils than web hosting.

How? GitHub.

### GitHub

GitHub is a hosting service for source code version control. It's used for programmers so they have an offsite savefile of their code. It also has free static website hosting. That's the bit that we're interested in.

We'll be using Jekyll Now, which is kind of the web equivalent of one of those prefab homes- they have all of the wiring done, and you're able to walk on in, and customise it to your tastes. No, I don't have any experience building houses, how did you know?

First step, you're going to want to create a GitHub account. Then, navigate to [Jekyll Now](https://github.com/barryclark/jekyll-now), and hit the 'Fork' button, which is right next to the 'Watch' and 'Star' button. This will create a clone of the prefab, which is 'your' website.

![Click the thing circled in red]({{site.baseurl}}/images/githubFork.png)

Go into the 'Settings' page, and for sake of keeping things clean, untick the features 'Wikis', 'Restrict Editing', 'Issues', and 'Projects'. Those are programming things.

Then, scroll down, and under the 'GitHub Pages' heading, set the dropdown in 'Source' to 'master branch'. This tells GitHub that we want them to host it as a page. Then go ahead and pick a theme.



Then, navigate to your DNS server, and input the following custom resource records.

Name: @, 		Type: A, 		TTL: 1h, 	Data: 192.30.252.153
												  192.30.252.154
Name: wwww, 	Type: CNAME, 	TTL: 1h, 	Data: rhysgraymusic.com

![obviously replace rhysgraymusic with your own site!]({{site.baseurl}}/images/dns.png)

### Making the site **yours**

What we're going to do is go to the site [prose.io](prose.io), which is essentially a site that prettifies all of the code, and makes it a lot easier to edit your blog posts.

#### Custom Domains
If you have a custom domain, enter it into that bit of the GitHub settings. You're going to need to change the CNAME registry to get it to properly redirect, though. So go to the CNAME file, and put it in there, both the subdomain and apex domain.

e.g.
www.rhysgraymusic.com
rhysgraymusic.com




You're going to want to go to the config.yml file, and fill in the deets- name, description, social links, etc.

Go to about.md and change up the about stuff. Tell your story.

### Hello, world!

Jekyll does a lot of the heavy lifting for you. One thing you can't mess up is the formatting of the titles of your posts- YYYY-MM-DD-Title-Goes-Here.md. That tells it when it was posted, and the title. Dashes for spaces. Easy.

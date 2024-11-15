---
title: Yes, I am blogging
date: 2024-11-13
draft: false
tags:
  - tag1
  - tag2
---

# Hey, this is awesome


### Just doing some stuff here

- Doing this


```bash
#!/bin/bash

# Step 1: Extract image filenames from blog posts
grep -oh '\[\[Pasted image [^]]*\.png\]\]' content/posts/posts/*.md | sed 's/.*Pasted image/Pasted image/' | sed 's/]]//' > images.txt

# Step 2: Copy images to Hugo static folder
xargs -a images.txt -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images

# Step 3: Update image links in blog posts
sed -i '' 's/!\[\[\(Pasted image [^]]*\)\]\]/![Image]\/images\/\1/g' content/posts/posts/*.md
```


!![Image Description](/images/Pasted%20image%2020241113171357.png)

!![Image Description](/images/Pasted%20image%2020241113171501.png)



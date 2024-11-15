---
title: I forgot to rename this
date: 2024-11-06
draft: false
tags:
  - tag1
  - tag2
---


# Test



!![Image Description](/images/Pasted%20image%2020241112120458.png)




```bash
#!/bin/bash

# Step 1: Sync posts from Obsidian to Hugo content folder using rsync
echo "Syncing posts from Obsidian..."
rsync -av --delete ~/Documents/neotokos/posts ./content/posts

# Step 2: Process Markdown files with Python script to handle image links
echo "Processing image links in Markdown files..."
python3 test.py

echo "Building the Hugo site..."
hugo

# Step 3: Add changes to Git
echo "Staging changes for Git..."
git add .

# Step 4: Commit changes with a message
echo "Committing changes..."
git commit -m "hey, another post"

# Step 5: Build the Hugo site


# Step 6: Deploy the public folder to the GitHub repository using git subtree
echo "Deploying to GitHub..."
git subtree push --prefix public git@github.com:thenetworkchuck/hugotest.git test

echo "All done! Site synced, processed, committed, built, and deployed."
```
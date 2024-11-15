---
title: "I'm so excited"
date: 2024-10-04
draft: false
tags:
  - tag1
  - tag2
---


# I am testing something 

- This will be quite the test to see how this works out. 
- I don't really know what I'm doing but I hope it works


# Messing with the tech


- As part of this post, I need to figure out how to get images synced

```bash
#!/bin/bash

# Step 1: Extract image filenames from blog posts
grep -oh '\[\[Pasted image [^]]*\.png\]\]' content/posts/posts/*.md | sed 's/.*Pasted image/Pasted image/' | sed 's/]]//' > images.txt

# Step 2: Copy images to Hugo static folder
xargs -a images.txt -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images

# Step 3: Update image links in blog posts
sed -i '' 's/!\[\[\(Pasted image [^]]*\)\]\]/![Image]\/images\/\1/g' content/posts/posts/*.md
```


```bash
#!/bin/bash

# Step 1: Extract all .png filenames from blog posts
# This will find any instance of a .png file in markdown files
grep -o '[^ ]*\.png' content/posts/posts/*.md | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder (compatible with macOS)
# Read from images.txt and copy files from the Obsidian media directory
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Update image links in blog posts
# Adjust image links to point to /images/ in each markdown file
sed -i '' 's/!\[\[\([^]]*\.png\)\]\]/![Image]\/images\/\1/g' content/posts/posts/*.md
```


![Image]/images/Pasted image 20241112111001.png


```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Update image links in blog posts
# Convert Obsidian-style links to standard markdown format with correct URL syntax
sed -i '' 's/!\[\[\([^]]*\.png\)\]\]/![Image Description]\/images\/\1/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
```

```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Update image links in blog posts
# Convert Obsidian-style links to correct markdown syntax for Hugo
sed -i '' 's/!\[\[\([^]]*\.png\)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
```


```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Update image links in blog posts
# Convert Obsidian-style links to Markdown with correct URL syntax, replacing spaces with %20
sed -i '' 's/!\[\[\([^]]*\.png\)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/neotokos/posts/*.md
sed -i '' 's/ /%20/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
```


```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Update image links in blog posts
# Convert Obsidian-style links to Markdown with correct URL syntax and replace spaces only in the image path
sed -i '' -E 's/!\[\[([^]]*\.png)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/neotokos/posts/*.md
sed -i '' -E 's/\(\/images\/([^) ]*) /\(\/images\/\1%20/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
```



```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Update image links in blog posts
# Convert Obsidian-style links to Markdown with correct URL syntax
sed -i '' -E 's/!\[\[([^]]*\.png)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md

# Step 4: Replace all spaces in image URLs with %20
sed -i '' -E 's/\(([^)]+)\)/\(\1\)/g; s/ /%20/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
```


```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Convert Obsidian-style links to Markdown links with correct syntax
# Only converts the format, leaving spaces untouched for now
sed -i '' -E 's/!\[\[([^]]*\.png)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md

# Step 4: Replace spaces with %20 **only within URLs that start with /images/**
# This specifically targets the URLs without affecting other parts of the file
sed -i '' -E 's|(/images/[^) ]*) |\1%20|g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
```


```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Convert Obsidian-style links to Markdown links with correct syntax
# Only converts the format, leaving spaces untouched for now
sed -i '' -E 's/!\[\[([^]]*\.png)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md

# Step 4: Continuously replace spaces with %20 only within URLs that start with /images/
# This ensures all spaces in image URLs are replaced without affecting other parts of the text
while grep -q '(/images/[^)]* )' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md; do
    sed -i '' -E 's|(/images/[^)]*) |\1%20|g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md
done
```



```bash
#!/bin/bash

# Step 1: Extract all .png filenames in the format `![Image Description](/images/Pasted%20image%20...%20.png)`
grep -oh '\[\[[^]]*\.png\]\]' /Users/networkchuck/Documents/neotokos/posts/*.md | sed 's/\[\[\(.*\.png\)\]\]/\1/' | sort | uniq > images.txt

# Step 2: Copy images to Hugo static folder
cat images.txt | xargs -I {} cp "/Users/networkchuck/Documents/neotokos/Attachments/{}" /Users/networkchuck/Documents/testblog/my-hugo-site/static/images/

# Step 3: Convert Obsidian-style links to Markdown links with correct syntax
# Only converts the format, leaving spaces untouched for now
sed -i '' -E 's/!\[\[([^]]*\.png)\]\]/![Image Description](\/images\/\1)/g' /Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts/*.md

# Step 4: Replace all spaces in /images/ URLs with %20 in a single command
sed -i '' -E 's|\(/images/[^)]*\)|\1|g; s| /images/|%20/images/|g'
```



```python
import os
import re
import shutil

# Paths
posts_dir = "/Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts"
attachments_dir = "/Users/networkchuck/Documents/neotokos/Attachments"
static_images_dir = "/Users/networkchuck/Documents/testblog/my-hugo-site/static/images"

# Step 1: Process each markdown file in the posts directory
for filename in os.listdir(posts_dir):
    if filename.endswith(".md"):
        filepath = os.path.join(posts_dir, filename)
        
        with open(filepath, "r") as file:
            content = file.read()
        
        # Step 2: Find all image links in the format ![Image Description](/images/Pasted%20image%20...%20.png)
        images = re.findall(r'\[\[([^]]*\.png)\]\]', content)
        
        # Step 3: Replace image links and ensure URLs are correctly formatted
        for image in images:
            # Prepare the Markdown-compatible link with %20 replacing spaces
            markdown_image = f"![Image Description](/images/{image.replace(' ', '%20')})"
            content = content.replace(f"[[{image}]]", markdown_image)
            
            # Step 4: Copy the image to the Hugo static/images directory if it exists
            image_source = os.path.join(attachments_dir, image)
            if os.path.exists(image_source):
                shutil.copy(image_source, static_images_dir)

        # Step 5: Write the updated content back to the markdown file
        with open(filepath, "w") as file:
            file.write(content)

print("Markdown files processed and images copied successfully.")
```
![Image Description](/images/Pasted image 20241112112055.png)





![Image Description](/images/Pasted image 20241112112338.png)




![Image Description](/images/Pasted image 20241112112852.png)






![Image Description](/images/Pasted image 20241112113113.png)



!![Image Description](/images/Pasted%20image%2020241112114055.png)









!![Image Description](/images/Pasted%20image%2020241112115325.png)




# Final Code - Mac/Linux

## Python Script

```python
import os
import re
import shutil

# Paths
posts_dir = "/Users/networkchuck/Documents/testblog/my-hugo-site/content/posts/posts"
attachments_dir = "/Users/networkchuck/Documents/neotokos/Attachments"
static_images_dir = "/Users/networkchuck/Documents/testblog/my-hugo-site/static/images"

# Step 1: Process each markdown file in the posts directory
for filename in os.listdir(posts_dir):
    if filename.endswith(".md"):
        filepath = os.path.join(posts_dir, filename)
        
        with open(filepath, "r") as file:
            content = file.read()
        
        # Step 2: Find all image links in the format ![Image Description](/images/Pasted%20image%20...%20.png)
        images = re.findall(r'\[\[([^]]*\.png)\]\]', content)
        
        # Step 3: Replace image links and ensure URLs are correctly formatted
        for image in images:
            # Prepare the Markdown-compatible link with %20 replacing spaces
            markdown_image = f"![Image Description](/images/{image.replace(' ', '%20')})"
            content = content.replace(f"[[{image}]]", markdown_image)
            
            # Step 4: Copy the image to the Hugo static/images directory if it exists
            image_source = os.path.join(attachments_dir, image)
            if os.path.exists(image_source):
                shutil.copy(image_source, static_images_dir)

        # Step 5: Write the updated content back to the markdown file
        with open(filepath, "w") as file:
            file.write(content)

print("Markdown files processed and images copied successfully.")

```


## Bash Script

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



## Final - Windows

C:\Users\chuck\Documents\my_second_brain\neotokos

### Python

```python
import os
import re
import shutil

# Paths (using raw strings to handle Windows backslashes correctly)
posts_dir = r"C:\Users\chuck\Documents\chuckblogtest\content\posts"
attachments_dir = r"C:\Users\chuck\Documents\my_second_brain\neotokos\Attachments"
static_images_dir = r"C:\Users\chuck\Documents\chuckblogtest\static\images"

# Step 1: Process each markdown file in the posts directory
for filename in os.listdir(posts_dir):
    if filename.endswith(".md"):
        filepath = os.path.join(posts_dir, filename)
        
        with open(filepath, "r", encoding="utf-8") as file:
            content = file.read()
        
        # Step 2: Find all image links in the format ![Image Description](/images/Pasted%20image%20...%20.png)
        images = re.findall(r'\[\[([^]]*\.png)\]\]', content)
        
        # Step 3: Replace image links and ensure URLs are correctly formatted
        for image in images:
            # Prepare the Markdown-compatible link with %20 replacing spaces
            markdown_image = f"![Image Description](/images/{image.replace(' ', '%20')})"
            content = content.replace(f"[[{image}]]", markdown_image)
            
            # Step 4: Copy the image to the Hugo static/images directory if it exists
            image_source = os.path.join(attachments_dir, image)
            if os.path.exists(image_source):
                shutil.copy(image_source, static_images_dir)

        # Step 5: Write the updated content back to the markdown file
        with open(filepath, "w", encoding="utf-8") as file:
            file.write(content)

print("Markdown files processed and images copied successfully.")

```

### Powershell

```powershell

# Step 1: Check if Git is initialized, and initialize if necessary
if (!(Test-Path ".git")) {
    Write-Output "Initializing Git repository..."
    git init
    git remote add origin git@github.com:thenetworkchuck/chuckblog.git
} else {
    Write-Output "Git repository already initialized."
}


# Step 2: Sync posts from Obsidian to Hugo content folder using robocopy
Write-Output "Syncing posts from Obsidian..."
$sourcePath = "C:\Users\chuck\Documents\neotokos\posts"
$destinationPath = "C:\Users\chuck\Documents\blog\chuckblog\content\posts"
robocopy $sourcePath $destinationPath /MIR

# Step 3: Process Markdown files with Python script to handle image links
Write-Output "Processing image links in Markdown files..."
python process_images.py

# Step 4: Add changes to Git
Write-Output "Staging changes for Git..."
git add .

# Step 5: Commit changes with a message
Write-Output "Committing changes..."
git commit -m "hey, another post"

# Step 6: Build the Hugo site
Write-Output "Building the Hugo site..."
hugo

# Step 7: Deploy the public folder to the GitHub repository using git subtree
Write-Output "Deploying to GitHub Master..."
git push -u origin master

Write-Output "Deploying to GitHub  Hostiger..."
git subtree push --prefix public git@github.com:thenetworkchuck/chuckblog.git hostinger

Write-Output "All done! Site synced, processed, committed, built, and deployed."

```
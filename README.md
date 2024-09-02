# Podcast Feed Generator
This GitHub Action converts a YAML file into a valid podcast feed. YAML offers a more readable and writable format compared to XML, making this tool ideal for podcast feed generation.

# Getting Started
  1. Enable GitHub Pages
  Go to Settings > Pages in your repository, and set the main branch as the source. This will create a URL for your page and make the content in the main branch accessible. Save this URL for the next step.
  2. Create Your YAML File
  Add a YAML file to your repository with the following structure:
```
yaml
title: <Podcast Title>
subtitle: <Podcast Subtitle>
author: <Author Name>
description: <Podcast Description>
link: <GitHub Pages URL>
image: <Artwork Location>
language: <Podcast Language e.g. en-us>
category: <Podcast Category e.g. Technology https://podcasters.apple.com/support/1691-apple-podcasts-categories>
format: <format of files e.g. audio/mpeg>
item:
  - title: <Podcast Episode Title>
    description: <Podcast Episode Description>
    published: <Date Published - e.g. Thu, 12 Jan 2023 18:00:00 GMT>
    file: <Filename e.g. /audio/TFIT01.mp3>
    duration: <duration e.g. 00:00:36>
    length: <length e.g. 576,324 (Get Info on your files)>
  ... Add more episodes as needed
``` 
3. Create a Workflow File
Set up a workflow file in your .github/workflows directory. Here’s a sample configuration:
```
name: Generate Feed
on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  generate-feed:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3
        
      - name: Run Feed Generator
        uses: your-username/podcast-feed-generator@main
```
Replace your-username with your GitHub username or organization.

4. Action Configuration
Ensure that the podcast-feed-generator action is available in your repository. You can use it directly or publish it to the GitHub Marketplace for broader use.

# Important Notes
Verify that your YAML file is properly formatted to prevent any issues.
Confirm that the GitHub Pages URL is correctly set up and accessible.
# License
This project is licensed under the MIT License. See the LICENSE file for more details.

---
title: Setup a Github Page
date: 2023-03-15 19:50:00 +0100
categories: [Wiki, Web]
tags: [github, website, portfolio]
---

# Github Pages

## Setup a Github Repo using Jekyll using a Chirpy theme

Follow the instructions on the [Chirpy Github Page](https://chirpy.cotes.page/posts/getting-started/).

Use this command prompt to display your page locally on your computer. This way you don't have to upload it to Github everytime you want to see your changes, which takes time.

```sh
sudo bundle exec jekyll s
```

You can access the page on [http://127.0.0.1:4000/](http://127.0.0.1:4000/).

## Create your first blog post

Puplish your first blog post by creating a new markdown file in your /\_posts/ directory. For more info check the [official docu](https://chirpy.cotes.page/posts/write-a-new-post/).

## Modify settings

Customize your webpage in the \_config.yml file.

If you want to add or substract a social media tag in the lower left corner, modify the /\_data/contact.yml file.

## Learn to use markdown

For details use the [GitHub wiki for markdown](https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### How do add pictures

```markdown
![description](_site/assets/img/picture.png "Hovertext (optional)")
```

![radar](/assets/img/Avatar_1.png "Hovertext (optional)")
_Image Caption_

### How to add links

```markdown
[displayed text](URL)
```

### How to add a table

```markdown
| Header 1 | Header 2 |
| :------- | :------- |
| 1        | 2        |
| 3        | 4        |
| 5        | 6        |
```

| Header 1 | Header 2 |
| :------- | :------- |
| 1        | 2        |
| 3        | 4        |
| 5        | 6        |

### How to add Check Boxes

This feature only works with Github

```markdown
- [ ] unchecked box
- [x] unchecked box
```

- [ ] unchecked box
- [x] unchecked box

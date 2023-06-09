---
title: Setup a Github Page
date: 2023-03-15 19:50:00 +0100
categories: [Wiki, Web]
tags: [github, website, portfolio]
---

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

### Emphasise

```markdown
**Bold Text**
```

**Bold Text**

```markdown
_Italic Text_
```

_Italic Text_

```markdown
~~Strikethrough~~
```

~~Strikethrough~~

### Description list

```markdown
Arduino
: a small microcontroller

Raspberry Pi
: a small computer running on a linux based OS
```

Arduino
: a small microcontroller

Raspberry Pi
: a small computer running on a linux based OS

### Block Quote

> This is a Block Quote.

### Prompts

```markdown
{: .prompt-tip }

> Type `tip` prompt.

{: .prompt-info }

> Type`info` prompt.

{: .prompt-warning }

> Type `warning` prompt.

{: .prompt-danger }

> Type `danger` prompt.
```

{: .prompt-tip }

> Type `tip` prompt.

{: .prompt-info }

> Type`info` prompt.

{: .prompt-warning }

> Type `warning` prompt.

{: .prompt-danger }

> Type `danger` prompt.

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
| Name      | Hobby        |
| :-------- | :----------- |
| Tommy     | Programming  |
| Lucas     | Martial Arts |
| Chrsitian | Photography  |
```

| Name      | Hobby        |
| :-------- | :----------- |
| Tommy     | Programming  |
| Lucas     | Martial Arts |
| Christian | Photography  |

### How to add Check Boxes

This feature only works with Github

```markdown
- [ ] unchecked box
- [x] unchecked box
```

- [ ] unchecked box
- [x] unchecked box

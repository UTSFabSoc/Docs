
> [!Warning] WIP
> - github deploy
> 	- common issues
> - quartz
> - editing the docs in obsidian
> - using github to clone the docs locally for editing 

The FabSoc docs (where you are right now) is a collection of markdown pages/files which is converted to a static website by Quartz and hosted through Github Pages. There's a few steps there so lets go through the process from markdown to live website.
## Markdown
Markdown is a markup language for writing formatted text using a simple plaintext editor, but you can also add in links to other pages making a connected "web" of information, great for documentation like this. 
You can even write markdown in notepad! it would look something like this:
```md
# Heading
some body text here
- Bullet point 1
- Bullet point 2
- Bullet point 3
*this text is in italics*
~~this text is crossed out~~
```

> [!done] This is the above would be formatted to:
> # Heading
some body text here
> - Bullet point 1
> - Bullet point 2
> - Bullet point 3
> *this text is in italics*
> ~~this text is crossed out~~

While it is very much possible to edit markdown in a simple text editor, it can be much easier to create clean formatting and setup more advanced things like links and tables by using a markdown editor such as Obsidian. 
In Obsidian, you can open up the entire FabSoc docs as a project and edit them locally, then when you're finished you can push the changes back to Github where it will automatically update the site. But how you ask?
## Github Deploy and Quartz
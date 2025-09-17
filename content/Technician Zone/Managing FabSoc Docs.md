
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

> [!done] The above would be formatted to:
> # Heading
> some body text here
> - Bullet point 1
> - Bullet point 2
> - Bullet point 3
> *this text is in italics*
> ~~this text is crossed out~~

While it is very much possible to edit markdown in a simple text editor, it can be much easier to create clean formatting and setup more advanced things like links and tables by using a markdown editor such as Obsidian. 
In Obsidian, you can open up the entire FabSoc docs as a project and edit them locally (load the `content` folder), 

> [!NOTE]- Previewing your changes
> If you would like to preview yoour changes before pushing to the live branch you can run `npm run docs` from the root folder of the repository: `Docs`
> This will host a version of the website locally at http://localhost:8080

When you are finished you can push the changes back to Github where it will automatically update the site. But how you ask?
## Quartz
In order to turn the markdown files into a site that can be hosted on the internet, we use Quartz. This layer converts the markdown into static html files ready for hosting. It's main configuration can be done from the `quartz.config.ts` file. For more advanced configuration please check the [Quartz Docs](https://quartz.jzhao.xyz/)
## Github Deploy
The final step in order to host the website is Github deploy. This is an automated process run on the Github servers which uses the quartz configuration to build and deploy the static website files. This should just work on its own but if you get a deployment error like below:
![[Pasted image 20250819211849.png]]
Then you'll need to go into the config at `Docs\.github\workflows\deploy.yaml` and figure out what's going wrong. last time we had issues it was due to outdated versions of the `artifiact-actions` being used so try checking those first if you get a similar error!

## All together now
1. Clone the GitHub repo for FabSoc docs https://github.com/UTSFabSoc/Docs
2. Open and edit the documentation in Obsidian or any other compatible markdown editors
3. Push your changes back to the FabSoc repo (or make a pull request if you don't have access to push directly)
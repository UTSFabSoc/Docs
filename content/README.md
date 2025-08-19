Welcome to the Fabsoc docs!
I just became co-owner of this and don't know what's meant to go here, but this is probably a good place to put some tips/troubleshooting for the docs themselves
## The documentation for the documentation
### Editing the docs
The easiest way to edit the docs is to clone the repository locally and open up the content folder in [Obsidian](https://obsidian.md/) 

When you're ready to publish your changes to live, push them to the main branch. That seems to automatically start a chain of GitHub actions to build and deploy the docs site at https://utsfabsoc.github.io/Docs/
### Troubleshooting 
An issue I ran into when trying to update this site was depreciated versions of the GitHub actions artifacts. If you get an error like below, try checking what the latest version of each artifact in `.github\workflows\deploy.yaml` is and updating them to latest (by changing the version number)

![[Pasted image 20250819211849.png]]
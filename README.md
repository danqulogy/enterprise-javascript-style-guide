# Enterprise Application Style Guide & Patterns
This guide documents some of the best practices for crafting code in the enterprise setting to enhance code maintainability and ease of picking up lagacy codebase for new developers.

## Angular Based Applications

- Organize your applications in modules, primarily core modules, feature modules and shared modules for cross-cutting concern.s

- A module's subfolders should be _typed folders_. This means folder names such as pipes, components, blocks, views, services, actions, stores, directives and etc.

- Organize a modules subfolder contents using an **index.ts** file, a technique known as **barrel** to reduce long import names. This is also implements the facade designed pattern hence some also calls it a **index.ts** a **facade file**.
The benefit is that, it ensures that there is only one place where you import your constructs which is pretty tidy than the _scatta waka way_. This also means that were you to move files around, changing directories for certain constructs, the barrel file is the only one where updating the paths to these constructs is needed. However, angular natively provides a way to achieve barrelling on the module level using it **ngModule** _decorator_ through the exports and _declaration_ property;


- Modules should be cohesive. That is to say they should be doing one and only thing.



- Root Modules should not export anything.

- export constructs can be done by adding the export keyword to each construct or using group export syntax. This will a matter of taste. For example `export {Cat, Dog}`


- By the way dependency injection has a cost, so if a component has too many dependencies it is time to revise and see whether your component is really taking on a single responsiblity.

- A word about providers. Both angular modules and components have access to a providers array through their decorators that we can add the `service` constructs. Since the arrival of Angular modules, the recommendation is not to use the providers array for components. The explanation is that specifiying it as a provider on module level easily descends to all components. However when a component instantiates a service the service instance will be only available to the child components and directives used in that component. That is limiting. But others may see it as a way of limiting the use of a particular service. Use my recommendation. After instantiating is done once, we don't want any deadlocks. If you can careful, then you may go the component level provisioning but for safety use Module level provisioning.
So the rule of thumb here is if you want to expose a service to your application, then put it in the Angular module's `providers` array. If you want to limit access to the service, the place it into a components `providers` array. The you will ensure it can only be reached by that component and its view children.















**Edit a file, create a new file, and clone from Bitbucket in under 2 minutes**

When you're done, you can delete the content in this README and update the file with details for others getting started with your repository.

*We recommend that you open this README in another tab as you perform the tasks below. You can [watch our video](https://youtu.be/0ocf7u76WSo) for a full demo of all the steps in this tutorial. Open the video in a new tab to avoid leaving Bitbucket.*

---

## Edit a file

You’ll start by editing this README file to learn how to edit a file in Bitbucket.

1. Click **Source** on the left side.
2. Click the README.md link from the list of files.
3. Click the **Edit** button.
4. Delete the following text: *Delete this line to make a change to the README from Bitbucket.*
5. After making your change, click **Commit** and then **Commit** again in the dialog. The commit page will open and you’ll see the change you just made.
6. Go back to the **Source** page.

---

## Create a file

Next, you’ll add a new file to this repository.

1. Click the **New file** button at the top of the **Source** page.
2. Give the file a filename of **contributors.txt**.
3. Enter your name in the empty file space.
4. Click **Commit** and then **Commit** again in the dialog.
5. Go back to the **Source** page.

Before you move on, go ahead and explore the repository. You've already seen the **Source** page, but check out the **Commits**, **Branches**, and **Settings** pages.

---

## Clone a repository

Use these steps to clone from SourceTree, our client for using the repository command-line free. Cloning allows you to work on your files locally. If you don't yet have SourceTree, [download and install first](https://www.sourcetreeapp.com/). If you prefer to clone from the command line, see [Clone a repository](https://confluence.atlassian.com/x/4whODQ).

1. You’ll see the clone button under the **Source** heading. Click that button.
2. Now click **Check out in SourceTree**. You may need to create a SourceTree account or log in.
3. When you see the **Clone New** dialog in SourceTree, update the destination path and name if you’d like to and then click **Clone**.
4. Open the directory you just created to see your repository’s files.

Now that you're more familiar with your Bitbucket repository, go ahead and add a new file locally. You can [push your change back to Bitbucket with SourceTree](https://confluence.atlassian.com/x/iqyBMg), or you can [add, commit,](https://confluence.atlassian.com/x/8QhODQ) and [push from the command line](https://confluence.atlassian.com/x/NQ0zDQ).
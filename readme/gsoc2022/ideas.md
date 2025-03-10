# GSoC 2022 Ideas

2022 is Joplin third round at Google Summer of Code. Detailed information on how to get involved and apply are given in the [general Summer of Code introduction](https://joplinapp.org/gsoc2022/index/)

**These are all proposals! We are open to new ideas you might have!!** Do you have an awesome idea you want to work on with Joplin but that is not among the ideas below? That's cool. We love that! But please do us a favour: Get in touch with a mentor early on and make sure your project is realistic and within the scope of Joplin. Just make sure your idea is within this year's theme:

- **Plugin development** - implementing new features using Joplin's plugin system.
- **External desktop applications** - build external Joplin applications by retrieving, creating or modifying notes via the Data API.
- **External server applications** - leverage the Joplin Server API to provide online features to Joplin users.

# Information for Students

These ideas were contributed by our developers and users. They are sometimes vague or incomplete. If you wish to submit a proposal based on these ideas, you are urged to contact the developers and find out more about the particular suggestion you're looking at.

Becoming accepted as a Google Summer of Code student is quite competitive. Accepted students typically have thoroughly researched the technologies of their proposed project and have been in frequent contact with potential mentors. **Simply copying and pasting an idea here will not work.** On the other hand, creating a completely new idea without first consulting potential mentors rarely works.

# List of ideas

## 1. Plugin system on mobile

The plugin system is currently available on desktop and CLI. We believe it could work on mobile too although some work will have to be done to make the plugin API compatible, as well as add a mechanism to load plugins.

Expected Outcome: Allow loading and running plugins on mobile

Difficulty Level: High

Skills Required: TypeScript, React Native

Potential Mentor(s): [PackElend](https://discourse.joplinapp.org/u/PackElend), [roman_r_m](https://discourse.joplinapp.org/u/roman_r_m), [laurent22](https://github.com/laurent22/)

## 2. Seamless desktop application updates

The desktop application currently supports automatic updates, however the process is not particularly smooth: the user is presented with a modal dialog, where they need to click "Download" and that opens the default browser to download the file. Then they need to run this file and go through the installer.

We would like to make this process smoother:

- The installer should be automatically downloaded in the background
- It should then install the app automatically when the next time the app is started
- And this should work at least on Windows and macOS (Linux may be special due to the different distribution methods)

Difficulty Level: Medium

Skills Required: TypeScript, React. Some knowledge of Electron and electron-builder.

## 3. Refactor the project documentation

The current documentation (under [joplinapp.org/help](https://joplinapp.org/help)) is mainly a giant README.md file and various smaller Markdown files under /readme. All this is then built into the HTML website by a script.

We would like to improve this by splitting the main readme into smaller sections, have a new menu that would reorganise the help into various topics, and of course the build script will need to be updated.

A good part of this project will be about researching how other projects organise their documentation, proposing a way that would work well for Joplin, and discussing your ideas with the mentors and users. This is still a technical project though since you will need to deal with TypeScript, Markdown, HTML and CSS (and any other technology that might help) to build the new documentation.

Difficulty Level: High

Skills Required: TypeScript, JavaScript, CSS, HTML, Markdown rendering.

## 4. Implement default plugins on desktop application

We would like to bundle certain plugins with the desktop application, such as the Backup or Rich Markdown plugin. Some process needs to be implemented so that they are bundled and updated automatically. You'll have to consider how it will work on CI, and across platform. The process should be fault tolerant and retry when something fails.

Difficulty Level: High

Skills Required: TypeScript, JavaScript, knowledge of Electron and GitHub Actions.

## 5. Implement a toolbar for the mobile beta code editor

We would like the Beta code editor to eventually become the main editor, and for that a number of changes need to be made. The main one would be the addition of a toolbar to it, to set the various styles, such as Bold, Bullet list, Header, etc. Additionally there are number of bugs that will have to be fixed to get the editor ready for production - you will find them in the list of issues (under the "high" and "mobile" label).

Difficulty Level: High

Skills Required: TypeScript, JavaScript, React Native, React Hooks. You'll also need to learn about CodeMirror 6 if you're not already familiar with it.

## 6. Improve integration of the richtext/WYSIWYG editor

Joplin offers a richtext/WYSIWYG typing experience alongside the Markdown editor but there are a number of areas that could do with improvement when it comes to integration with Joplin as a whole.

Areas for consideration include increasing compatibility with Joplin-wide keybindings (many are currently static), limiting features of the editor not compatible with markdown formatting, reducing the impact of data changes caused by swapping between editors.
Also read the document about limitations of the editor: [https://joplinapp.org/rich_text_editor/](https://joplinapp.org/rich_text_editor/)

Difficulty level: High

Skills Required: Typescript, Javascript, CSS, HTML, Markdown rendering. You will also need to learn about TinyMCE if you're not already familiar with it.

## 7. Improve PDF export

Joplin uses Chrome's built-in print to PDF function which is very limited. This can be improved by using a 3rd party library to convert notes to PDF. Applies to desktop and CLI versions.

Potential benefits:
* Export multiple notes as a single PDF
* Embedding attachments (see https://github.com/laurent22/joplin/issues/5943)
* Delay export until the note is fully rendered (https://discourse.joplinapp.org/t/ability-to-delay-pdf-export-to-allow-plugins-to-render/22159)

Difficulty level: Medium

Skills Required: Typescript, Javascript.

## 8. Replace built-in PDF renderer with a library

Just like with export, Joplin relies on the built-in PDF renderer to show PDF attachments. Replacing it with a 3rd-party library has a number of advantages:
* Joplin can preserve PDF viewer state when a note is re-rendered. For instance currently after opening and closing settings, PDF are reset to the 1st page.
* It may be possible to link to a specific page or even a location within a PDF document.
* Annotate PDF documents from Joplin

Difficulty level: Medium

Skills Required: Typescript, Javascript.

## 9. Rebuild file system sync on Android

A recent update broke file system synchronization on Android, as applications are now required to use a new API to access storage. Currently there are no libraries that would proxy this API for React Native. If we want to get file system sync working again it has to be written from scratch.

Difficulty level: High

Skills Required: Android, Java/Kotlin, Typescript.

## 10. Tablet layout

On wide screens devices like tables Joplin could use a different layout, e.g. with note list always showing, or have both editor and viewer visible at the same time.

Difficulty Level: Medium

Skills Required: React, Typescript, CSS.

## 11. Improve plugin search and discoverability

As there are more and more plugins it would be good to improve how they are discovered, and to improve search - in particular improve search relevance. We are open to hear ideas about this, but a few things that could be done, for example are:

- Improve the [page that lists all the plugin](https://github.com/joplin/plugins#readme) by adding a download count (based on stats.json) and make the list sortable by download count.
- In the app, use the info from stats.json to order the plugin - those with more downloads going on top for example
- Create a dynamically generated page (using GitHub Actions) under joplinapp.org that shows some recommended plugins, trending plugins, etc. similar to [Add-ons for Firefox](https://addons.mozilla.org/en-GB/firefox/)

Those are just ideas and we're open to hearing more from you.

Difficulty Level: Medium

Skills Required: Typescript, CSS, GitHub Actions.

# More info

- Make sure you read the [Joplin Google Summer of Code Introduction](https://joplinapp.org/gsoc2022/index/)
- To build the application, please read [BUILD.md](https://github.com/laurent22/joplin/blob/dev/BUILD.md)
- And before creating a pull request, please read the [pull request guidelines](https://joplinapp.org/gsoc2022/pull_request_guidelines/)

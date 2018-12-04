---
id: page-plugin
title: Qordoba - i18next
header_title: Qordoba - i18next
header_icon: /assets/images/icons/plugins/GitHub-enterprise-integration.png
breadcrumbs:
  Plugins: /ecosystem
nav:
  - label: Getting Started
    items:
      - label: Configuration
  - label: Usage
    items:
      - label: Sending parameters
      - label: Known Issues
---

The Qordoba i18next plugin makes it easy to sync locales files between any i18next project and Qordoba.

## Getting Started

To get started, clone or download the repo from GitHub. Use `npm` to install the repo in the root directory and download dependencies for the plugin. If you want to run the example app, `cd` into the `/example` directory and run `npm install`.

Before starting, visit Qordoba.com, set up an account and create a new project. If you are running the example app, set English as the source language, and pick a few target languages. Select **JSON** (not **JSON(custom)**) as your file type. Set up translation memories, etc. 

Once the app is created, get values for the `consumerKey`, `organizationId`, and `projectId`.

After setting up a project and getting your configuration keys you are ready to run the example app.

## Qordoba-i18next-plugin file structure.
The plugin's file structure is as follows:

```
├── root
│   ├── example // example app for project
│   ├── lib // transplied ES6 code
│   ├── src
│   │   ├── index.js // i18next-node-fs-backend (see below)
│   │   ├── qordoba.js // main functionality, handles sync between qordoba and filesystem
│   │   ├── utils.js // helper functions for i18next-node-fs-backend
│   ├── test
│   ├── gulpfile.js // handles 'gulp build' command
│   ├── package.json
```

Example App File Structure.

```
├── example
│   ├── build  // compiled ES5 code
│   ├── locales
│   │   ├── en // i18next-node-fs-backend (see below)
│   │   │   ├── namespace1.json // this is where keys are linked to translated strings
│   │   │   ├── namespace2.json
│   │   ├── qordoba // built by plugin
│   │   │   ├── es, da, etc  // all your target languages
│   │   │   ├── files
│   │   │   │   ├── source.json // metadata for source files, timestamps, fileIds, etc
│   │   │   │   ├── target.json // metadata for target files, timestamps
│   ├── public
│   ├── src
│   │   ├── assets
│   │   ├── components
│   │   ├── index.js // main entry point for react app
│   ├── style
│   ├── server
│   │   ├── server.js // main entry point for express server (CONFIG GOES HERE)
│   ├── webpack.config.js
│   ├── package.json
```

To run the example app, go into the server and add you keys.
- ORGANIZATION_ID // id of your qordoba organization
- PROJECT_ID // id qordoba give you when you create a new project
- MILESTONE_ID // id of milestone (eg. 'Proofreading' ) that you want to pull translations from
- CONSUMER_KEY // secret key to access API
	
Then 'npm run build' to transplile your configuration into build directory.

If you just created a new project, check for the qoroba folder in 'root/example/locales', delete this folder if it exists. The plugin handles synching your source keys / strings from 'i18next/<source language>'. It will take all your source files, copy them over to the qordoba directory, then upload these files to qordoba and download and build folders and namespaces for all target languages.

### Scripts

Root Directory
- 'gulp build' - transpliles ES6 code from src -> lib into ES5. Provides runtime support for promises.
- 'npm test' - run mocha tests for plugin.

Example app
- 'npm run build' - transpiles ES6 code from src -> build. Builds production bundle for app.
- 'npm start' - starts express server in server/server.js. Serves example app to localhost:3000

### Prerequisites

- Familiarity with the i18next internationalization framework.

- I18next-node-fs-backend. This is what handles loading the locales files into the i18next framework. 

### Prerequisites for the example app

- React-18next internationalization plugin - a higher order component to provide the i18next functionality to react components.

- I18next-express-middleware - middleware to use i18next in express.js. Supports multiloading of backend routes, etc.

## Running the tests

'npm test' in the root directory

## Built With

* [i18next](http://i18next.com/) - Internationalization ecosystem
* [i18next-node-fs-backend](https://github.com/i18next/i18next-node-fs-backend/) - I18next node backend for node.js
* [react-i18next](https://github.com/i18next/react-i18next) - Internationalization for react done right.
* [i18next-express-middleware](https://github.com/i18next/i18next-express-middleware) - express middleware for i18next


## Versioning

// to do once published to npm

## Authors

* **Erik Suddath** -

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


Qordoba-Node-Backend-Plugin for i18next using Qordoba files API
  * Source can be loaded via npm
  * Will sync the data source (source language files) between i18next and Qordoba
  * Will handle checking Qordoba for updates, downloading updated files and writing translations to file system
  * Will serve files from Qordoba locales folder in fs
  
### Run options

## Pull 
  * Download the latest translations manually from the command line (gulp)
  * Download the latest translations real time from Qordoba Files API
  a) Plugin will check timestamps from Qordoba files API on every incoming request 
  b) Will download any updated files, write them to the fs, and update the resource bundle in i18next
  * Load the latest translation on a preset interval
  a) Will check Qordoba for file updates on specified interval

## Push
  * Upload the latest source language files manually from the command line (gulp)
  * Will upload files to Qordoba web app via the Files API so the translations can be created, edited, proofread, and pushed (deployed) for use by the qordoba-nodejs-plugin 

```
{
  // Qordoba organization id
  organization_id: '[ORGANIZATION ID]',
  // Qordoba project id
  project_id: '[PROJECT ID]',
  // Qordoba consumer key
  key: '[KEY]',
  // Path To Save Qordoba Keys To
  qordobaLocalesPath: '[PATH TO QORDOBA KEYS]',
  // Download Options
  download: '[COMMAND LINE | REAL TIME | INTERVAL ]',
  // Upload Options (Source Language, { version: ‘’ })
  upload: '[COMMAND LINE]'
}
```

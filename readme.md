# iOS Tutorials

This is a repo dedicated to the iOS codebar Workshop. These materials can be used during a normal codebar workshop as long as a coach is there with the skill set.

## Building the tutorials

We are now using [docusaurus](https://docusaurus.io) to build our tutorials. You will need npm installed on your computer to get started.

1. Fork this repo.
2. Using a terminal, navigate into `src/website`.
3. Run `npm i` to install all dependencies.
4. Run `npm run start` to run the website locally.

## How to add a new tutorial page

1. Create the page in the `docs` folder (make sure it follows the same structure as the others).
2. Any images you need can be places in a folder in `docs/assets`.
3. Make sure you link to it in the `website/sidebars.json` properly.
4. To test the sidebars you need to stop running it locally, then run it again.
5. If required, add a section in `website/pages/index.js` so everyone knows it exists!

## How to deploy

We're using GitHub pages to host whatevers in the `docs` folder in root. Unfortunately this is a little bit of a manual process at the moment but you need to:
1. Navigate to `src/website`.
2. Run `npm run build`.
3. Copy the `ios-tutorials` folder into the root of this directory.
4. Delete the `docs` folder (it's okay, we're going to fix this in a second).
4. Rename `ios-tutorials` to `docs`.

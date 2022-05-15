---
sidebar_position: 1
---

# Squiz Matrix (CMS) v6

Setting up a new Squiz Matrix (6) website.

## Setup

Get started by **creating a new site**.

### What you'll need

- Clone the **[Squiz Matrix starter kit](https://github.com/qld-gov-au/design-system-starter)** and unzip (if required)
- A basic understanding of Squiz Matrix CMS configuration

### Creating a sub site

- It is recommended you create your site under a folder with appropriate naming convention
- Go to 'Import Assets from XML tool'
- Under 'Files to import' select the cloned starter kit (XML)
- Import assets under root is optional (use as required)
- The import will take a few minutes to complete and may return warnings
- Once this is complete the 'Details' screen will display (the newly imported site will now be visible in the asset tree)
- Configure 'status' and 'name' (internal only) e.g. DCHDE - Demo website
- Select 'Save' in top right
- Once this has completed you will now see 'Git repository' as a section under the same 'Details' screen

### Setting up the Gitbridge

- Enter the 'Git URL' for the **[Design system](https://github.com/qld-gov-au/design-system)** 
- Under 'Sub Directories' enter 'dist' to refer to the compiled/distributable files within this repository 
- No secret key is required for a public repository 
- Under 'Morphing' ensure 'Git File Bridge' is selected
- Under 'Current Repository' > 'Branch, tag or commit' enter 'master' to refer to the master release
- Next to 'Git URL' select 'Clone Repo' (this might take several minutes, if this fails retry by selecting 'Update'
- Once this is complete, check all paint layouts:

### Debug layouts for import related issues
- Under 'Demo site' > Paint layouts > Page Default > For each (Landing page, Content page, Component page, News result page, News detail view) > Open Type formats > Default Format (for each) 

```PHP
  %begin_asset_metadata_displayBanner^eq:default%
    <!-- Default Banner -->
    %globals_asset_contents_paint_383:22037%
    ...
```
- '383' is a bug (the import creates an asset reference that does not exist)
- Under 'Demo site' > Components > Configuration > Inspect the asset number for 'Non CT Paint Layout'. Use this asset number to replace '383' in the paint layouts mentioned above. 

### Setting up a custom theme (override)





```bash
cd my-website
npm run start
```

The `cd` command changes the directory you're working with. In order to work with your newly created Docusaurus site, you'll need to navigate the terminal there.

The `npm run start` command builds your website locally and serves it through a development server, ready for you to view at http://localhost:3000/.

Open `docs/getting-started.md` (this page) and edit some lines: the site **reloads automatically** and displays your changes.

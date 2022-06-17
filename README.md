# Docusaurus CloudCannon Base Site

A barebones Docusaurus site.

## CloudCannon Configuration File

To configure the CMS, a `cloudcannon.config.yml` file has been created at the root of the repository. This contains the following sections:

### Collections

In `collections_config.docs` we specify a `docs` collection. This will be shown in the CloudCannon sidebar and will allow editors to make changes within this collection.

To match Docusaurus' default URL behavior, we use the `[full_slug]` url placeholder.

These URLs are used in the CloudCannon interface for opening previews and generating screenshots.

### Paths

In `paths` we specify the path for both our `uploads` and `static` directories. This ensures that assets uploaded in CloudCannon will be placed inside the `static` directory, and will be linked relative to the same directory.

| editor's file | uploaded file    | output url |
|---------------|------------------|------------|
| image.png     | static/image.png | /image.png |

### Editables

In `_editables.content` we specify the toolbar options that editors will see in the [CloudCannon Content Editor](https://cloudcannon.com/documentation/articles/introducing-the-content-editor/).

***

> To read the full documentation for `cloudcannon.config.*` files, see [Setting global configuration](https://cloudcannon.com/documentation/articles/setting-global-configuration/) at the CloudCannon Documentation.

## Connecting the Site to CloudCannon

*   When connecting this repository to CloudCannon, choose the `Other` option for your static site generator. When prompted for **Command Line Options**, use the following values:

    | field           | value         |
    |-----------------|---------------|
    | Install Command | npm i         |
    | Build Command   | npm run build |
    | Output Path     | build         |

    > `mkdocs` is already installed on the CloudCannon build image, so the install command is only needed for our theme. If you removed `theme: material` from `mkdocs.yml`, you could leave the install field blank.

    > `build` is the default directory that Docusaurus will use for its output.
    > Additionally, adding `node_modules/` in **Preserved Paths** will help speed up subsequent builds.

## Done!

That's all — once your site builds you will be able to browse, edit, and add to the `docs` collection in CloudCannon.

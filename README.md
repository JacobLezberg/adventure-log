<p align="center">
	<a href="https://github.com/JacobLezberg/adventure-log/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/JacobLezberg/adventure-log"></img></a>
  <a href="https://github.com/JacobLezberg/adventure-log/commits/main">
    <img src="https://img.shields.io:/github/last-commit/jacoblezberg/adventure-log"></img></a>
  <a href="https://github.com/JacobLezberg/adventure-log/actions/">
    <img src="https://img.shields.io/github/workflow/status/jacoblezberg/adventure-log/ci"></a>
</p>

# D&D Adventure Log

This project is based on the wonderful [MkDocs Obsidian Template](https://mara-li.github.io/mkdocs_obsidian_template/) from [Mara-Li](https://github.com/Mara-Li).


## How to View
The *best* way to view this content is in [Obsidian's](https://obsidian.md/) reading mode. All of the links, formatting, embedded media, and page previews will looks as they were originally intended, plus you get features like Graph Mode. Unfortunately, Obsidian Publish is a paid feature, so you can only view the vault from inside Obsidian after cloning the repo. If you don't want to download anything, the next best way to view the contents of the vault is by visiting [The Adventure Log](https://jacoblezberg.github.io/adventure-log/).


## How to Contribute
Whenever a commit is pushed to the `main` branch of this repository, GitHub invokes MkDocs (a documentation-focused static site generator) which processes all of the Markdown files to build the website. Therefore, you don't need any tools except git, but there is some other software that would be helpful.

### Required
- [Git](https://git-scm.com/downloads)

### Recommended
- [Obsidian](https://obsidian.md/) for creating and editing Markdown files
- [Python](https://www.python.org/downloads/) for local previews (and for usage of the `obs2mk` script if desired)
- [VSCode](https://code.visualstudio.com/Download) for editing YAML, HTML, or other misc. files

Once you've installed the tools, 
1. Clone this repo. One way this can be done is by executing the command `git clone git@github.com:JacobLezberg/adventure-log.git` in the Terminal.
1. In Obsidian, open the folder `adventure-log/docs` as your Vault. The `.obsidian` folder should be processed automatically to give you the proper settings, but if not, make sure that `Use [[Wikilinks]]` is enabled and `New link format` is set to "Shortest path when possible".
1. Make any edits you wish (more on that later). All of the D&D content should be inside the `docs` folder (`assets` is part of MkDocs Material theme, so don't worry about that for now).
   1. Note that if you include two files with the exact same name but different extensions (e.g. `Spectator.md` and `Spectator.png`) the short Wikilinks-style links might get confused and link to the wrong thing. I just renamed images to avoid this (e.g. `Spectator_image.png`).
   1. I think this is the point at which you would run the `obs2mk` script, but I'm not entirely sure when it's needed and whether we need its features. There is some documentation of it below.
1. Preview your changes, if desired, by running `mkdocs serve` from the `adventure-log` directory. Assuming there are no errors, it will give you a local webpage that should mirror the one that would be deployed to GitHub Pages once you push your changes.
   1. You must install the python packages in order to run `mkdocs` locally. If you aren't using Conda or an equivalent, I recommend creating a Python virtual environment first with `py -m venv .venv` and activating it with `.venv/Scripts/activate`. Then the required packages can all be installed at once with `py -m pip install -r requirements.txt` and they'll be isolated from any other Python projects you may have.
   1. <details>
      <summary>Full list of Python packages (from template)</summary>
      
      - [MkDocs](https://www.mkdocs.org/getting-started/) : `pip install mkdocs`
      - [Material MkDocs](https://squidfunk.github.io/mkdocs-material/getting-started/) using `pip install mkdocs-material`
      - [Mermaid2](https://github.com/fralau/mkdocs-mermaid2-plugin) with `pip install mkdocs-mermaid2-plugin`.
      - [Roamlinks](https://github.com/Jackiexiao/mkdocs-roamlinks-plugin) : `pip install mkdocs-roamlinks-plugin`
      - [mkdocs-obsidian](https://pypi.org/project/obs2mk/) : `pip install obs2mk`
      - [mkdocs-awesome-pages](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin) : `pip install mkdocs-awesome-pages-plugin`
      - [mkdocs-tooltipster](https://github.com/Mara-Li/mkdocs-tooltipster-links-plugin)
      - [mkdocs-embed-file-plugins](https://github.com/Mara-Li/mkdocs_embed_file_plugins)
      </details>
1. Send your changes to the remote repository:
   1. `git pull` will pull down changes other people have made and incorporate them into your local working copy of the repo. If those changes clash with any of yours, you will be prompted to resolve the merge conflicts.
   1. `git status` will list the created, modified, and deleted files
   1. `git add X` will add file `X` to the "staging area" (if `X` is `.` it will add all changed files)
   1. `git commit -m "<message>"` will "commit" the changes to the staged files with a description
   1. `git push` will push your local commit(s) to the remote repository. Much of the power of git comes from its branch management, but we probably won't need that since this project isn't code-based. By default you will be on the `main` branch, and if you don't specify a target branch your commits will be pushed to the upstream of your current branch (i.e. local `main` --> remote `main`)
   1. If you want to learn more about git, I recommend [this website](http://think-like-a-git.net/) once you're comfortable with the basics.
1. GitHub (via MkDocs) will automatically regenerate the website. Give it a minute to redeploy before expecting changes to be visible (you can check the status in detail from the `Actions` tab of Github)


## Customization
The MkDocs Material theme has settings in the `mkdocs.yml` file.
- If you want to change the color palette, [refer to this](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/).
- The logo, favicons, js, and css can all be found in the `docs/assets` folder
- MkDocs also has hundreds of plug-ins ("extensions") that I haven't played around with at all [and can be found here](https://github.com/mkdocs/mkdocs/wiki/MkDocs-Plugins).
- Watch out for features marked "Insider." Apparently MkDocs Material Theme is *sponsorware* so there are some premium features we can't use.
- There is lots of useful documentation [here](https://squidfunk.github.io/mkdocs-material/) under the `Getting Started`, `Setup`, and `Reference` tabs.


## Editing
Documentation for Markdown syntax (including some Obsidian special features) can be found [here](https://help.obsidian.md/How+to/Format+your+notes).

### Templates
I made a few file templates in the `docs/templates` folder corresponding to different types of pages. The best way to use these is to create a new (blank) note in Obsidian, then press `Ctrl+T` to open the "Insert Template" menu, and select the desired template. These should help keep layouts and frontmatter consistent.

### Frontmatter
You can add a number of different properties to the frontmatter of a markdown file which essentially work as metadata but can control the way these tools interact with the files. Frontmatter must be at the top of the file and formatted in one of the following ways:
```
---
key: value
key: [value 1, value 2]
key:
  - value a
  - value b
---
```

#### Obsidian [(Documentation)](https://help.obsidian.md/Advanced+topics/YAML+front+matter)
- `aliases`: Alternate names for Obsidian to recognize and suggest links. For example, we have a page named `Glasstaff.md` but we want Obsidian to suggest backlinks to that page from any occurrence of `Iarno Albrek`, as they are the same character.
- `tags`: Tags for searching/sorting published content. ~~[MkDocs can use them too](https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags/)~~ *EDIT: That's a paid plugin for the MkDocs Material theme, so the tags are only for Obsidian*
- `cssclass`: I haven't played with this. Might be better to ignore and just handle any CSS overrides through MkDocs.

#### MkDocs [(Documentation)](https://www.mkdocs.org/user-guide/writing-your-docs/#meta-data)
- `template`: Note that this is an HTML template, not a Markdown template
- `title`: An override for the displayed name of a page. Also changes it in navigation. Good for letting Obsidian links be intuitive (without having ugly URLs with spaces in them).
- `description`: I'm not entirely sure how this is used. If it's for SEO, it's useless for us.
- `image`: Adds an image (needs <relative_link.format>). I'm not sure where/how this appears.
- `tags`: See above.

#### MkDocs Obsidian Script (Included as part of the MkDocs Obsidian Template)
- `category`: Alternate way to set folder structure. The special value `hidden` will exclude the file from the generated site (from `awesome-pages` plugin).
- `share`: Seems like it can act as a whitelist for publishing files, but we're publishing the vault contents by default so no need for this.
- `update`: Using the value `false` seems like it will lock the file from updating. Not very useful.

### Compatibility
From [Mara-Li](https://github.com/Mara-Li)'s documentation of the script:
> So, with the configuration I have done, the mkdocs support :
> - Folder note: the file needs to be named “index” (instead of the name of the folder)
> - Admonitions
> - Wikilinks and relative links
> - Highlight and tilde markdown
> - Mathjax and Mermaid 
> - Embed files (entire file, inline, heading)
> - Custom Attribute, as [CM6 Attribute (with tags)](https://github.com/nothingislost/obsidian-cm6-attributes/releases), [Markdown Attribute](https://github.com/valentine195/obsidian-markdown-attributes) and [Contextual Typography (with tags)](https://github.com/mgmeyers/obsidian-contextual-typography).
>
> I didn't found a way to embed file with wiki links for the moment. Because of the strange behavior of roam links, these embedded file will be rendered as image. The script will take care of this bug. 

---

<details>
<summary>Stuff from original README I haven't cleaned up yet</summary>

## Script
The script need one key, to share the file. You can configure the key in the configuration of the script.


# MkDocs Obsidian
## Utilities and interest
*A vast part of the script is taken from my previous project, YAFPA*

The script will care about some things you can forget :
- Moving your image in assets ;
- Change the admonition from the plugin to material admonition (mainly for codeblocks)
- Remove Obsidian comment (`%% text %%`) 
- **Create a folder structure** based on the `category` key. Without it, the note will be created in `docs/notes`.

If you use the `--meta` option, it will also add, in the **original file** a link to the blog. 

⚠️ If the script crashes for any reason at the moment where the script updates the frontmatter, you can lose some file.

## Usage
```powershell
usage: obs2mk [-h] [--git | --mobile] [--meta] [--keep] [--config]
                   [--force] [--filepath FILEPATH | --ignore]

Create file in docs and relative folder, move image in assets, convert
admonition code_blocks, add links and push.

optional arguments:
  -h, --help            show this help message and exit
  --git, --g, --G       No commit and no push to git
  --mobile, --shortcuts, --s, --S
                        Use mobile shortcuts fonction without push.
  --meta, --m, --M      Update the frontmatter with link
  --keep, --k, --K      Keep deleted file from vault and removed shared file
  --config, --c, --C    Edit the config file
  --force, --d, --D     Force conversion - only work if path not specified
  --filepath FILEPATH, --f FILEPATH
                        Filepath of the file you want to convert
  --ignore, --ignore-share, --no-share, --i, --vault
                        Convert the entire vault without relying on share
                        state.
```

At the first start of the script, it will ask you :
- The **absolute path** of your vault and blog in your PC.
- The key you want to use to share the file (default : `share`).

This file will be in your `site_package/mkdocs_obsidian` folder.
> On pyto, it will be directly in site_package

You can reconfigure the option with `obs2mk --config`.

By default, the script will remove all file that doesn't exist in the vault, and file where you remove the share (`share: false`, or removed the key). You can keep all these file with `--k`. Empty folder will be also removed in this process.  

> A little note about "Folder Note": If the file has the same name as the last part of `category`, it will be renamed `index` during conversion.  
> However, this prevents the file from being deleted if its source is deleted from your vault: in this case, you have to delete it manually. 

> ⚠️ You need to configure and use an alias to cite an index file ; By default, this alias is `(i)` but it can be configured in environment configuration. 
> Some example : `[[Real file|(i) Alias]]` → `[[index|Alias]]` | `[[Real File|(i)]]` → `[[index|Real file]]`

> Git Note : If a folder is empty, it will be "erased" in git. 

### Share one file
To share **only** one file : `obs2mk --f FILEPATH`. It will :
- Update the state status in original file (`share: true`)
- Re-write the file if exist or create it in the folder you put in `category` 
This option will pull the file, regardless of what is the `share` state.

### Share “all” files
You can share multiple documents using the `share: true` key, in frontmatter. The script will scan your entire vault and automatically convert the file with this key.
There is two options :
- By default, the script will compare with the older version and write only if changement are detected, based on the content of the file and the last modified time. 
- Using `--force` will force the re-writing. 

You can force to skip the update with `update: false` in the frontmatter : the file, no matter what, will not be updated. 

#### Share the entire vault

Using the command `--ignore` will ignore the `share` state : you can share your entire vault using that, whatever the state is. By default, it will not overwrite file already exist (and not different), so the `--force` option can also be used.

`usage: obs2mk [-h] [--git | --mobile] [--meta] [--keep] [--config]
                   [--force] [--ignore]`

### Mobile

<details><summary><i>Read more</i></summary>
	
The mobile option is similar to the `git` option but with some nuance. When used to publish a single file, you can use only the file name, without the path.

:warning: Be careful though, in case you have several files with the same name, the script will take the first file found. 

This option can be used especially with the "Shortcuts" application on IOS, to share a file directly from the share sheet.

One file usage : `obs2mk --mobile --f "filename"`
All file usage : `obs2mk --mobile`

Mobile supports all previous option, including `--ignore`.

### IOS 
Using :
- [a-shell](https://holzschu.github.io/a-Shell_iOS/) (Free)
- [Working Copy](https://workingcopyapp.com/)
You can update the docs.

First, in a-shell, run `pickFolder` and choose the folder of your vault, and rerun `pickFolder` to choose the folder where are the blog data (you need to clone with [Working Copy](https://workingcopyapp.com/))
After, do `showmarks` and copy the two path in any note app. Check if the path is not broken because of the paste!
You can also do :
```bash
cd 
showmarks > bookmark
vim bookmark
```

Here is a blank sheet to help you if you want to manually write / edit it :
```
vault=
blog_path=
blog=
share=
index_key=
```
With :
- `vault`: Vault Absolute Path
- `blog_path` : Blog repository absolute path
- `blog` : Blog link (same as `site_url` from `mkdocs.yml`)
- `share` : your wanted share key ; by default : `share`
- `index_key`: For folder note citation

Before running the shortcuts, you need to install all requirements, aka :
```
pip install obs2mk
obs2mk --config
```

After, in a-shell, you can use the same option as on a PC.
</details>

## Customization
There are some files to customize the script :
- You can create [custom admonition with material docs](https://squidfunk.github.io/mkdocs-material/reference/admonitions/) and adding the name in `custom_admonition.yml`. 
- You can completely exclude some folder of your vault with `exclude_folder.yml`. You can exclude specific path as `folder1/subfolderA` etc.
- Using the `\docs\assets\css\custom_attributes.css` you can create specific aspect for your tags, and it also adds compatibility with CM6 Attribute and Contextual Typography. 

## Limitation
- **Nested admonition doesn't work for the moment.** I don't use it a lot, but if you want, you could improve the script or create a mkdocs plugin to care of that. 
- The script will not delete the file and folder if you change the `category` key. Beware of this. 
- Share “all” can be long on big vault. 
- File with same name can have some problem while scanning because I don't keep your folder structure. Please, beware of this! Don't forget, you can use `title` if you want a specific name (and this name already exist). 


## Support
The script can work on any platform that support python. The script doesn't use Cpython, so don't worry about it for IOS.

### Obsidian

You can integrate the script within obsidian using the nice plugin [Obsidian ShellCommands](https://github.com/Taitava/obsidian-shellcommands).  
You could create two commands :
1. Publish everything: Alias `Publish` with `obs2mk --obsidian`
3. Publish one specific file : Alias `Publish {{title}}` with `obs2mk --obsidian --f {{file_path:absolute}}`

With the `0.10` you could also add event shortcuts :
- File menu event `Publish {{event_file_name}}`: `obs2mk --obsidian --f "{{event_file_path:absolute}}"`
- Folder Note event `Publish {{event_folder_name}}`: `obs2mk --obsidian --f "{{event_folder_path:relative}}\{{event_folder_name}}.md"`

You can use :
- [Customizable Sidebar](https://github.com/phibr0/obsidian-customizable-sidebar)  
- [Obsidian Customizable Menu](https://github.com/kzhovn/obsidian-customizable-menu)  
To have a button to share your file directly in Obsidian !

If you have more questions, don't forget to read the [Q&A](https://github.com/Mara-Li/mkdocs_obsidian_template/wiki/Q&A/) !

</details>
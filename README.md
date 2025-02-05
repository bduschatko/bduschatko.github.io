How to add pages to your navigation menu:

Add or change links and names in the \_layout/base.html file


This repository contains the code necessary for a custom Jekyll theme. The key components are described below in order to facilitate custom changes.

## The \_layouts directory

All webpage content can be written in markdown files - within these markdown files, layouts are specified that represent the HTML code userd to render the markdown. This directory contains all of the HTML code to build web pages from markdown. The purpose of the HTML files in this directory is only to specify the layout of content on the page - all styling, including CSS code and language settings, occurs in other locations and should be imported within each layout file. 

Different layouts can be used for different pages, and they're all contained in \_layouts. In this repository, we define a base.html layout that is used to build all other pages. 

Jekyll commands can be inserted into these layouts. For example, in the base.html layout file you'll find we use a Jekyll import command {% include head.html %} which imports additional HTML code stored in the \_includes directory. 


## The \_includes directory

Jekyll helps organize code and clean clutter by abstracting stylistic code away from the layouts. In the layouts above, we utilized the import functionality to include external HTML code in the layouts. This directory is one location for some of this code - it is the HTML specific components that define the pages.

## The \_sass directory

In addition to the \_includes, partial CSS code is stored here. Jekyll will later compile the .scss files into complete CSS prior to injecting the CSS into the the locations we've imported them in any files under \_includes. As such, this directory should be used for all artistic changes to the webpage. 

The files here are particularly useful for creating classes that will later be used by HTML elements, with the code being injected into the HTML header/style block.

## The assets directory

As suggested by the title, this contains any assets used by the page. As an example, in order for Jekyll to compile the partial CSS code into complete code, we can add imports of the partial CSS code to the css assets at assets/css/style.scss. This file gets processed to build the stylesheet for the entire website, which can later be linked to in the \_includes files. Note that the asset file we write will have a scss ending but the linked stylesheet in any HTML code should be the .css file - the reason is that Jekyll will compile this code prior to launching the site.



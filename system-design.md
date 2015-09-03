# ifpress.org

## System Design

### Requirements

 * authors must log in to manage stories
 * users can view without logging in
 * authors have ability to
   * log in to back-end administration system
   * create new projects
   * authorize users to access projects
   * import a ulx or blorb file to a project
   * create/edit templates
     * properties
       * header
       * footer
       * navigation
         * standard
         * custom
       * 1 column
       * 2 columns
       * 3 columns
       * 4 columns
     * identify responsive/mobile/desktop capability
     * layout engine
       * Bootstrap
     * background color
     * foreground color
     * default font
     * mono-spaced font
     * static image(s)
   * edit layout of page for every turn in walk-through
     * create intro page(s)
     * create tutorial page(s)
     * create base page
       * add global content types and designs
     * create pages by filter (inherits base page)
       * default
       * chapter
       * turn range
       * time range
       * custom ('template' content type is returned)
     * add content types to page for selected filter
   * publish story
     * privately
       * author has access
       * selected users have access
     * publicly
     * feedback system enabled/disabled
     * social networking enabled/disabled
 * users have ability to
   * when not logged in
     * browse public stories
     * play public stories
     * comment on public stories
     * chat with others playing same public story
   * when logged in
     * browse public and private stories
     * play public and private stories
     * comment on public and private stories
     * chat with others playing same public or private story
 * JSON-based templates and configuration (not XML)

## Stories

IF Stories are compiled using Inform 7 (inform7.com). To be compatible with ifpress.org, they will need to include I7 extensions found at the fyrevm-web github repository.

There will be a Core extension that takes care of the basic necessities.

Then there will be additional and optional extensions based on each author's interests.

One of the basic requirements will be for the author to implement ifpress.org settings, so that's going to be a separate extension (you can create FyreVM games without publishing to ifpress.org). Included will be a walk-through (comma separated list of commands to complete game and touch as many parts of the story as possible). This will likely flow through a "ifpress" content type and return JSON.

## Templates
## Pages
## Content Types

### Base Content Types from FyreVM Core

 - main - main text emitted from story progress
 - prompt - prompt or textual prefix to command line (optional)
 - location-name - name of current story location
 - score - current score (optional)
 - time - current time within story (optional)
 - death - text emitted upon death within story (optional)
 - end-game - text emitted when story ends (optional)
 - turn - number of turns taken in story (optional)
 - story-info - (JSON) meta data used to build "about" and "credits" information
 - score-notify - text emitted when score changes (optional)

### Extended Content Types from ifpress.org extension (required)

 - walk-through - (JSON) list of commands to traverse to build content model from uploaded story

### Extended Content Types for Images for ifpress.org (optional)

 - image list - (JSON) list of image file names

## Widgets

Widgets are the visual representations of content types found within a given story. This is where each story can display context in visually different ways. Any given content type may have many different related widgets since there are many different ways of displaying the same content.

Some widgets may encapsulate multiple content types too. An example of this might be a standard status line, which contains the location name, the turn, and the score. Here's an example widget in source form:

```
  <div class="ifp-status-line">
    <span class="ifp-left">{{location-name}}</span>
    <span class="ifp-right">{{score}}</span>
    <span class="ifp-right">{{turn}}</span>
  </div>
```

## Themes
## Administration
## Publishing
## Security
## Self-Hosting
## Host on ifpress.org



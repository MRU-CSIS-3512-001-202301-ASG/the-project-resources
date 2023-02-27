# Suggested Milestones

## Week of `2023-01-09`
- [ ] Sketch out page layouts.
- [ ] Get photos over to Cloudinary.
- [ ] Code up rough versions of admin pages (Login, Browse/Filter), using hard-coded data & minimal styling.
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-01-16`
- [ ] Admin pages still use hardcoded data, but are now more polished (perhaps even responsive).
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-01-23`
- [ ] Filters on Browse/Filter working on hard-coded data.
- [ ] Login has server-side validation.
- [ ] Browse/Filter sorting on hard-coded data working.
- [ ] last Browse/Filter sort used "remembered" via cookies. 
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-01-30`
- [ ] Browse/Filter now populated from database.
- [ ] Server-side validation of rating changes in place.
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-02-06`
- [ ] Able to properly authenticate into Browse/Filter page using database data.
- [ ] Redirection occurring (both on login and attempt to view Browse/Filter w/o login).
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-02-13`
- [ ] Admin pages fully functional (as per the functionality req's doc), or very close to it.
- [ ] [Dead Drop API](api-details.md#dead-drop-api) functional.
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-02-20 (READING WEEK)`
- [ ] Take a break? catch up if you're behind?

## 📌Week of `2023-02-27`
_Remember there are are 2 primary "views": Default View and Single Photo View that technically live on one page (`index.html`)...but you don't have to have it that way._
 
- [ ] Create an html page for each view that uses hard-coded data; nothing needs to be interactive at this point, so clicking on things and typing in values doesn't have to actually _do_ anything yet - you're simply trying to get the layout and "look" of the different views solidified.
    > _Remember this though: you're not going to be keeping these individual pages!_
- [ ] Pay attention to what elements are on your pages (things like `<li>` and `<img>`, for example) and begin to figure out what JavaScript objects will be necessary to create those elements.
    > _For example, your `<img>` tags are going to need unique `src`, `srcset`, and `alt` attributes. Capturing these in simple JS objects will be a lifesaver._
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-03-06`
_Since we won't be talking about how to get JSON from an API endpoint for a while, you can still simulate this by making your own hard-coded JSON and using that instead._
- [ ] Start generating the content for your views dynamically:
  - [ ]  Put the JSON representing the elements of your views into files, generate JS objects from that JSON, and use those objects to create DOM elements that you insert into the views.
    - [ ]  You probably are wondering where you're getting this JSON from! You know how to make a JSON endpoint in PHP, so create the endpoints you need, go to the endpoints in a browser, and copy-paste the results into some files.
  - [ ]  By the end of this process, you should now be dealing with a single html page (`index.html`) and not multiple ones.
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-03-13`
_You should be able to start adding interactivity to your page this week._
- [ ] Identify every element on your page that needs to react to users (either via clicking or typing) and add necessary event handlers.
    > _Remember to use event delegation whenever required!_
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-03-20`
_By the end of this week, your entire site is basically working, but will have some rough edges that can be fixed before the deadline._
- [ ] By the end of this week, you should be replacing your hard-coded JSON data with JSON pulled in from your API endpoints.
- [ ] Cache required data into local storage. 
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd).

## Week of `2023-03-27`
- [ ] Fine-tuning, bug fixes, touchups, and submission.
- [ ] Write at least one entry in the [project journal](instructions.md#project-journalmd). 

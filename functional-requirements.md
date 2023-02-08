# Functional Requirements

There are a lot of requirements! I'll continue adding and organizing them over the first couple of weeks. Welcome to the world of large, complex projects. 😁

To get full marks on The Project, you'll need to complete them all.

## General Requirements

- [ ] No jQuery, React, or any such 3rd-party JS libraries are used.
- [ ] All code you don't create yourself is referenced in your code as comments. If it's code you found online, it should only be a few (like 3 to 5) lines and you should include a link to where you found it. If you use code that was created through the help of a peer, cite them. You do not have to cite code you've been given in tutorials or lectures. **Egregious examples of academic dishonesty have the potential to give you a big fat zero on this assignment. Neither of us wants that.**
- [ ] Any database work must be done using PDO, not mysqli.
- [ ] All database queries involving `$_GET` or `$_POST` data must use prepared statements.

## Requirements for All Pages

- [ ] All pages have zero errors when validated by the [W3C Markup Validation Service](https://validator.w3.org/s). (Warnings are OK, though not great. I'd spend _some_ effort to remove them - but their presence will NOT affect your mark!)
- [ ] All pages look reasonable at Mobile L and Laptop L sizes on Google Chrome.  
    > _**Aside**: This isn't because I'm a Google fanboy, or because other sizes are not important. It's because I need to limit options, lest testing your pages becomes a nightmare for both of us._

## Requirements for the Admin Pages

### Login Page

- [ ] The landing page for the admin pages is called `admin.php`.
- [ ] The landing page shows a login form of some kind.
- [ ] The password field of the login form obfuscates the password being entered.
- [ ] The login form uses **server-side** validation.
  - [ ] There is **no client-side validation** present on the login form.   
    > _**Aside**: I want to make sure you have a grip on basic server-side validation and adding client-side validation here makes it harder for you and me to test that._
  - [ ] If a user enters in a username/password combination that is not found in the `administrators` table, a useful - but not too-revealing - message displays on the form **and** the form fields still have their previously-entered values.
- [ ] If the user authenticates correctly, the login status is saved using PHP session state, and the form redirects to the **Browse/Filter Page**.
- [ ] Authentication uses PHP's `password_hash()` and `password_verify()` functions.
  - [ ] `password_hash` uses the `PASSWORD_BCRYPT` algorithm with a cost of 12.  

### Browse/Filter Page

- [ ] This page shows, at a glance, thumbnails of photos **that have been rated by the user with userID 23**, along with their associated country, city, latitude, longitude, and rating. You pick the number of photos to show on the page and how you order the entries by default.
- [ ] When a user goes to this page without being logged in, they should be redirected back to the **Login Page**. Detection of whether the user is logged in is done through PHP sessions. 
- [ ] There is an intuitive way to sort the entries in ascending and descending order by rating and by city.
  - [ ] The last sort used is stored in a cookie that lasts for 24 hours so that if the user comes back to the site at some time in that period, this sort automatically happens.
- [ ] There is an intuitive way to filter the entries by country, city, and rating.
  - [ ] This must be done using PHP, not JS.  
    > _**Aside**: You'll be doing client-side filtering in the second half of the course. I want to make sure you can do filtering **both** ways._
  - [ ] The filters are either "or" filters (_"I want to find all images in Calgary or have a rating of 3"_) or "and" filters (_"I want to find all images in Calgary that have a rating of 3"_). Your choice - but it should be obvious to a user which it is.
  - [ ] If the filter produces no results, that is clearly indicated to the user - they shouldn't be thinking _"huh - there's nothing being shown...does that mean there are no results, or does it mean the page is broken?..."_
- [ ] There is an intuitive way to change the rating of an entry.
  - [ ] When a rating is changed, the corresponding data is updated in the necessary table in the database.
  - [ ] When a rating is changed, there is a visual cue to the user that the update has happened.
  - [ ] Server-side validation occurs to ensure the rating is an integer between 1 and 5, inclusive on both ends.
  - [ ] There is an intuitive way to log out; this destroys the current session and returns the user to the **Login Page**.

---

## Requirements for the API

- [ ] The API endpoints shown in the [api-details document](api-details.md) are fully and correctly implemented.
- [ ] When an API endpoint is consumed in the browser, the response headers in the inspector show `Content-Type: application/json`.

_Further API endpoints will be necessary once work begins on the public-facing site._

---

## Requirements for the Public-Facing Site

_Although there is only one "page" for the public-facing site - `index.html` - it actually has 2 "views": we'll call them the `Default View`, where users will spend most of their time, and the `Single Photo View`, which users will see when they select a photo. Thanks to JavaScript, we'll be able to show and hide the different views as needed._


### General Requirements

- [ ] The public-facing site has one and only one html page: `index.html`; that is also the only html page in the submitted GitHub repo.
- [ ] When a user goes to `index.html`, they see the Default View.
- [ ] All `<img>` tags displaying travel photos use `srcset` and `sizes` to create responsive images. (See this [MDN reference](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images#how_do_you_create_responsive_images) for guidance.)
  - [ ] All travel photos are served by Cloudinary at reasonable sizes. (This is my way of saying that you should not be using CSS to make huge images look small.)
- [ ] Tables are not used for layout.
- [ ] No embedded or inline JavaScript is present; all JavaScript is contained in external files.
- [ ] The `innerHTML` property is not used in any JS files.
- [ ] No alerts are used.
- [ ] Only specified data is stored in `session storage` and/or `local storage`. (_I'm trying to stop the tendency of some students to store **everything** in the browser!_)

### Default View Requirements

#### Country Listing

- [ ] An alphabetically-sorted list of country names is visible.
  - [ ]  If no filter is active, then all the countries in the database are shown.
  - [ ] If a filter **is** active, then only countries that match the filter are shown.
- [ ] Country names are initially obtained via a `fetch` from an API endpoint of your own devising. (_Hint: you will find it useful if you don't just grab the country **names** but also the **ISO** codes as well!_)
  - [ ] To improve the performance of the page, these names are saved in **local storage** after the initial `fetch`. 
  - [ ] If country names are already available in local storage, these names are used instead of using a `fetch`.

#### City Listing

- [ ] When a user has selects a country, event delegation is used to display an alphabetically-sorted list of cities in that country.
  - [ ] If there are no cities available for that country, then that is clearly indicated to the user.
- [ ] City names are always obtained via a `fetch` from an API endpoint of your own devising.

#### Filters

- [ ] There is an obvious way to filter countries by name; this filtering is case-insensitive and matches the start of the name. (_So `ca` should show `Canada`, but not `Jamaica`._)
- [ ] There is an obvious way to filter countries that have or do not have photos.
- [ ] Filters have no Submit buttons - they filter immediately on user entry.
- [ ] Only one filter is active at a time; if another filter is engaged, any previously engaged filters are cleared.

#### Country Information

- [ ] When the user clicks on a country in the **Country List**, event delegation is used to display the selected country's information:

    - [ ]  name
    - [ ]  area
    - [ ]  population
    - [ ]  capital name
    - [ ]  currency
    - [ ]  domain
    - [ ]  description
    - [ ]  languages (see below)
    - [ ]  neighbouring countries (see below)
    - [ ]  country map (see below)

 
##### Languages Requirements

_Look carefully at the data in the `Languages` column in the `countries` table -  you'll see some languages listed that contain a hyphen and regional information (e.g., en-CA for Canadian English eh). You'll need to deal with this!_

- [ ] The language's full name is displayed, not the ISO code.
- [ ] Language information is initially obtained via a `fetch` from an API endpoint of your own devising.
  - [ ] To improve the performance of the page, appropriate info is saved in **local storage** after the initial `fetch`. 
  - [ ] If language info is already available in local storage, it is used instead of using a `fetch`.


##### Neighbouring Countries Requirements

- [ ] The full name of neighbouring countries is displayed, not ISO codes. (_Hint: remember my previous hint in [Country Listing](#country-listing) about storing ISO codes with your country names? That might make your life easier here._)

#### City Information

- [ ] When the user clicks on a city in the City List, event delegation is used to replace any country information that was displayed with the selected city's information:
    - [ ] name
    - [ ] population
    - [ ] elevation
    - [ ] timezone

#### Travel Photos

- [ ] When a user clicks on a country or city, event delegation is used to display any photos from that location at a reasonable size.
  - [ ] If there are no photos for that location, that is clearly indicated to the user.
- [ ] As images are clickable, this is indicated to the user by changing the cursor when it's over a photo.

### Single Photo View Requirements

- [ ] When a photo is selected in the **Default View**, the page will display the Single Photo View.
- [ ] The photo shown is appropriately large for this view at both Laptop and Mobile sizes.
- [ ] In addition to the photo itself, the corresponding `title`, `user name`, `city`, `country`, and `description` are also displayed.
- [ ] A Google map showing a marker at the photo's latitude and longitude is present.
- [ ] The Exif info for the photo - `model`, `exposure`, `aperture`, `focal length`, and `iso` - are present.
- [ ] The colour information (5 dominant colours - look in the database!) for the photo is displayed in a way such that both the hex code and an appropriately coloured shape (like a box, or circle) are present for each colour. 
- [ ] The photo's ratings, along with the first name and last name of the user associated with each rating, are present, and sorted in descending order.
- [ ] There is an obvious way for the user to close this view and return to the **Default View**.
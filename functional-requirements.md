# Functional Requirements

There are a lot of requirements! I'll continue adding and organizing them over the first couple of weeks. Welcome to the world of large, complex projects. 😁

To get full marks on The Project, you'll need to complete them all.

## General Requirements

- [ ] No jQuery, React, or any such 3rd-party JS libraries are used.
- [ ] All code you don't create yourself is referenced in your code as comments. If it's code you found online, it should only be a few (like 3 to 5) lines and you should include a link to where you found it. If you use code that was created through the help of a peer, cite them. You do not have to cite code you've been given in tutorials or lectures. **Egregious examples of academic dishonesty have the potential to give you a big fat zero on this assignment. Neither of us wants that.**
- [ ] Any database work must be done using PDO, not mysqli.

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

## Requirements for the API

- [ ] The API endpoints shown in the [api-details document](api-details.md) are fully and correctly implemented.
- [ ] When an API endpoint is consumed in the browser, the response headers in the inspector show `Content-Type: application/json`.

_Further API endpoints will be necessary once work begins on the public-facing site._

## Requirements for the Public-Facing Site

_These will be added later as we get closer to Reading Week._

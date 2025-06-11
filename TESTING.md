# Testing

Website testing is the process of evaluating a website to ensure it meets specified requirements, functions correctly, performs efficiently, is secure, and provides a positive user experience. It is a critical phase in the web development lifecycle, aiming to identify defects, errors, or missing functionalities before the website is launched or updated, ensuring a high-quality product for end-users. 

This document is also linked to a README.md on project specifics and other technical data such as running the site.
[README.md](./README.md)

# Table of Contents
- [Testing](#testing)
- [Table of Contents](#table-of-contents)
  - [CSS validation](#css-validation)
  - [style.css](#stylecss)
- [HTML validation](#html-validation)
  - [index.html](#indexhtml)
  - [plants.html](#plantshtml)
  - [events.html](#eventshtml)
  - [gallery.html](#galleryhtml)
  - [subscribe.html](#subscribehtml)
  - [success.html](#successhtml)
  - [Summary](#summary)
- [Lighthouse](#lighthouse)
- [autoprefixer for other browsers](#autoprefixer-for-other-browsers)
- [Screen Reader](#screen-reader)
- [Bowser Compatibility](#bowser-compatibility)
- [Device Compatibility](#device-compatibility)
- [Bugs and know issues in development](#bugs-and-know-issues-in-development)
- [User Acceptance Stories – Roots and Shoots Website](#user-acceptance-stories--roots-and-shoots-website)
  - [1. Subscribe to Newsletter](#1-subscribe-to-newsletter)
  - [2. Responsive Navigation](#2-responsive-navigation)
  - [3. Date of Birth Validation](#3-date-of-birth-validation)
  - [4. Social Media Links](#4-social-media-links)
  - [5. Accessibility and Keyboard Navigation](#5-accessibility-and-keyboard-navigation)
  - [6. Form Validation Errors](#6-form-validation-errors)
  - [7. Custom Styling and Branding](#7-custom-styling-and-branding)
- [Further testing](#further-testing)
- [Roots and Shoot Website – Testing Table final](#roots-and-shoot-website--testing-table-final)


## CSS validation

CSS validation is the process of checking your CSS code to ensure it follows the official syntax rules defined by the W3C (World Wide Web Consortium). 
It helps you catch errors, improve browser compatibility, and write cleaner, more maintainable styles so that other developers can work on your code if required. - W3C

## style.css

![css validation](/testing-images/css_validation.jpg)

**Errors fixed**

- Removed unused font weight
- Removed solid is not a border-radius value : 6px solid

![css validation](/testing-images/css_passed.jpg)

# HTML validation

HTML validation is used to check whether your HTML code follows the official standards and syntax rules defined by the W3C (World Wide Web Consortium). 
Validating your HTML helps ensure your website works correctly, is accessible, and is easier to maintain. Validating HTML also enhances search engine optimization (SEO) 
and ensures consistent display across different browsers.  - W3C

## index.html

![Validation of index.html](/testing-images/index_validation.jpg)

- All issues resolved

![Validation of index.html](/testing-images/index_passed.jpg)

## plants.html

![Validation of plants.html](/testing-images/plants_validation.jpg)

Unresolved validation, changing of these suggested elements breaks the layout of the page

![Unresolved plants.html validation](/testing-images/plants_validation_unresolved.jpg)

Further research assisted with the below fix to line 345, missing div tag.

- All issues resolved

![Validation of plants.html](/testing-images/plants_passed.jpg)

## events.html

![Validation of events.html](/testing-images/events_validation.jpg)

- All issues resolved

![Validation of events.html](/testing-images/events_passed.jpg)

## gallery.html

![Validation of gallery.html](/testing-images/gallery_validation.jpg)

- All issues resolved

![Validation of gallery.html](/testing-images/gallery_passed.jpg)

## subscribe.html

![Validation of subscribe.html](/testing-images/subscribe_validation.jpg)

- All issues resolved

![Validation of subscribe.html](/testing-images/subscribe_passed.jpg)

## success.html

![Validation of success.html](/testing-images/success_validation.jpg)

- All issues resolved

![Validation of success.html](/testing-images/success_passed.jpg)

## Summary

Minor tweaks to formatting and the addition of closing tags have been added.
Site is now CSS and HTML validated


# Lighthouse

Lighthouse is an open-source, automated tool created by Google to analyse and improve the quality of web pages. It audits various aspects of a webpage, including performance, accessibility, SEO, 
and progressive web app (PWA) practices, and generates a report with suggestions for improvement. - Google

![Lighthouse results](/testing-images/lightHouse_results.jpg)

Test results are all green, no action required.

# autoprefixer for other browsers

style.css amended according to autoprefixer

# Screen Reader

Tested using Windows Narrator, no issues found.

# Bowser Compatibility

![powerMapper](/testing-images/powerMapper.jpg)

- Edge
- Chrome
- Safari
- Firefox

# Device Compatibility

Essential testing process to make sure that the website preforms well across multiple device types.

![Am I Responsive](/testing-images/amiresponsive.jpg)
- Testing cross platform for usability, no issues found.


# Bugs and know issues in development 

**Defects Fixed**

1. Subscribe.html
- Output of submitted form is YYYY-MM-DD, desired output is DD-MM-YYYY
- dateFormat: "d-m-Y", //Changed dateFormat to reflect UK format

2. Subscribe.html
- Able to submit a form without inputting a DOB in the required field.
- Added the following code from Stack Overflow, tested and confirmed working

// Prevent form submission if DOB is empty
    document.querySelector('form').addEventListener('submit', function (e) {
        if (!dateInput.value) {
            e.preventDefault();
            alert("Please enter your date of birth.");
            dateInput.focus();
        }

![Subscription testing image](/testing-images/subscription_testing.jpg)

3. Burger menu subscibe button is too wide on smaller screens.

![Burger menu subscibe button too wide](/testing-images/navBar_changes.jpg)

-  Added the following -nav-spaced ms-auto- to the navBar class to allign it right when burger menu is expanded. Also removed redundant ms-lg-3. Made changes to all pages.
  
![navBar code changes](/testing-images/navBar_code_changes.jpg)

4. Nested Google maps are not responsive on smaller screens.

![Nested Google maps are not responsive on smaller screens](/testing-images/google_maps_responsive.jpg)

- Added h-100 d-flex flex-column with flex-grow-1 on the paragraph to make the text fill out the available space. 
- Also added map-responsive class with custom styling.

5. Plants text area is different heights on different screens.

![Plants text area is different heights on different screens.](/testing-images/plants_scaling_issue.jpg)

![Plants text area is different heights on different screens resolution.](/testing-images/plants_scaling_resolved.jpg)

6. Modal shift page left when clicking on an image.

![Modal shift page left when clicking on an image.](/testing-images/modal_issue.jpg)

Added the following code to stop the shift of the Modal

![Modal shift page left when clicking on an image.](/testing-images/modal_issue_resolved.jpg)

7. Back to Home button was styled incorrectly on success.html

![Back to Home button was styled incorrectly on success.html](/testing-images/incorrect_btn_styling.jpg)

- Custom button class added.


**Defects Unresolved**

subscribe.html
- You are able to put an unrealistic DOB into the field, this is outside of the scope of this project so it wont be resolved.

subscribe.html

- You can enter any length of number, validation happens on only 1 digit.

![Back to Home button was styled incorrectly on success.html](/testing-images/number_length.jpg)


# User Acceptance Stories – Roots and Shoots Website

## 1. Subscribe to Newsletter

**Story:**  
As a visitor, I want to subscribe to the Roots and Shoots newsletter so that I can receive monthly updates about plants and events.

**Acceptance Criteria:**  
- Given I am on the subscription page  
- When I fill in all required fields and click submit  
- Then I should be redirected to a success page displaying my submitted details

**Tasks:**  
- [Done] Ensure all form fields (name, email, phone, DOB, address) have `required` validation  
- [Done] Create `success.html` page to display submitted data  
- [Done] Ensure form uses `GET` or `POST` method appropriately  
- [Done] Sanitize and handle form data properly  
- [Done] Style the success page to match branding

---

## 2. Responsive Navigation

**Story:**  
As a user on any device, I want the navigation menu to adjust for mobile and desktop so that I can navigate the site easily.

**Acceptance Criteria:**  
- Given I am using a small-screen device  
- When I tap the hamburger menu  
- Then the navigation options should expand visibly and be clickable

**Tasks:**  
- [Done] Use Bootstrap’s responsive navbar with toggler icon  
- [Done] Ensure toggle menu works on mobile  
- [Done] Verify all links are accessible and functional  
- [Done] Style expanded menu for readability on small screens  
- [Done] Test with browser dev tools at multiple breakpoints

---

## 3. Date of Birth Validation

**Story:**  
As a parent signing up my child, I want the form to restrict sign-ups for children under 4 years old.

**Acceptance Criteria:**  
- Given I enter a birthdate under 4 years ago  
- When I try to submit the form  
- Then I should be blocked from submitting and shown an appropriate alert message

**Tasks:**  
- [Done] Set up Flatpickr with `maxDate` of today minus 4 years  
- [Done] Add JS validation for empty or invalid DOB input  
- [Done] Display alert if DOB does not meet age requirement  
- [Done] Test DOB logic using past/future edge cases

---

## 4. Social Media Links

**Story:**  
As a user, I want to follow Roots and Shoots on social media so that I can stay engaged via Instagram, Facebook, and X.

**Acceptance Criteria:**  
- Given I click on a social media icon in the footer  
- When I do so  
- Then I should be taken to the appropriate social media page in a new browser tab

**Tasks:**  
- [Done] Ensure all icons have correct external links  
- [Done] Add `target="_blank"` and `rel="noopener"` to each link  
- [Done] Use accessible labels (`aria-label`) for screen readers  
- [Done] Verify links open properly in new tabs  
- [Done] Confirm icons are styled and hover correctly

---

## 5. Accessibility and Keyboard Navigation

**Story:**  
As a user with accessibility needs, I want to navigate the site using only my keyboard so that I can access all features.

**Acceptance Criteria:**  
- Given I use the Tab key  
- When I navigate through the page  
- Then all focusable elements (links, buttons, inputs) should be reachable and visibly focused

**Tasks:**  
- [Done] Ensure all interactive elements are focusable  
- [Done] Apply visible `:focus` styles  
- [Done] Verify tab order follows logical flow  
- [Done] Use semantic HTML for structure (e.g. `<main>`, `<nav>`)  
- [Done] Test with screen reader if available

---

## 6. Form Validation Errors

**Story:**  
As a user, I want to know when a form field is missing or incorrectly filled so that I can correct it before submitting.

**Acceptance Criteria:**  
- Given I leave a required field empty or enter an invalid value  
- When I attempt to submit the form  
- Then I should see a message telling me what needs to be corrected

**Tasks:**  
- [Done] Use built-in HTML validation (`required`, `type`, `pattern`)  
- [Done] Add custom JS validation for enhanced feedback (e.g., DOB)  
- [Done] Show user-friendly error messages  
- [Done] Prevent form submission if errors are present  
- [Done] Highlight invalid fields visually

---

## 7. Custom Styling and Branding

**Story:**  
As a first-time visitor, I want the site to look visually appealing and match the Roots and Shoots brand so that I trust its quality.

**Acceptance Criteria:**  
- Given I view any page  
- Then I should see consistent use of colors, fonts, and the Roots and Shoots logo

**Tasks:**  
- [Done] Apply consistent branding styles across all pages  
- [Done] Use custom stylesheet (`style.css`) with theme variables  
- [Done] Ensure logo is displayed and scaled properly  
- [Done] Check colours contrast for accessibility  
- [Done] Validate font consistency and layout spacing

# Further testing

# Roots and Shoot Website – Testing Table final

| **Test Case ID** | **Page / Feature**        | **Test Description**                          | **Expected Result**                                   | **Status** | **Notes / Bugs Found**              |
|------------------|---------------------------|-----------------------------------------------|-------------------------------------------------------|----------- |-------------------------------------|
| TC001            | Home (index.html)         | Load home page                                | Page loads within 3 seconds, no visual glitches       | Pass       |Tested in multiple locations         |
| TC002            | Navigation Bar            | Click “Plants” link                           | Navigates to **plants.html**                          | Pass       |                                     |
| TC003            | Navigation Bar            | Click “Events” link                           | Navigates to **events.html**                          | Pass       |                                     |
| TC004            | Navigation Bar            | Click “Gallery” link                          | Navigates to **gallery.html**                         | Pass       |                                     |
| TC005            | Navigation Bar            | Click “Subscribe” link                        | Navigates to **subscribe.html**                       | Pass       |                                     |
| TC006            | Plants Page               | Check content loads                           | Plant information loads and images display properly   | Pass       |                                     |
| TC007            | Events Page               | View event list / calendar                    | Events display correctly with Google maps             | Pass       |                                     |
| TC008            | Gallery Page              | View images                                   | All images load, modal works when images are loaded   | Pass       |                                     |
| TC009            | Subscribe Page            | Submit form with valid email, with form filled| Redirects to **success.html**                         | Pass       |                                     |
| TC010            | Subscribe Page            | Submit form with invalid email                | Validation error shown                                | Pass       |                                     |
| TC011            | Subscribe Page            | Submit form with missing data, name, number.. | Validation error shown                                | Pass       |                                     |
| TC012            | Success Page              | Load after successful subscription            | Shows confirmation message with confirmation output   | Pass       |                                     |
| TC013            | 404 Error Page            | Visit non-existent page (e.g., /fake.html)    | Custom 404 page is displayed                          | Fail       |Added a 404.html and tested          |
| TC014            | Mobile Responsiveness     | Test across mobile and tablet devices         | Layout adapts correctly on all screen sizes           | Pass       |                                     |
| TC015            | Load Speed                | Test performance (Lighthouse)                 | Page loads < 3s, score > 80%                          | Pass       |Tested with Lighthouse               |
| TC016            | Accessibility (A11y)      | Use screen reader, keyboard nav, alt text     | Site is fully navigable and readable                  | Pass       |Tested with end user                 |
| TC017            | Broken Links              | Check all site links manually or with crawler | No broken or dead links                               | Pass       |                                     |
| TC018            | SEO & Meta Tags           | Inspect page head tags                        | All pages have proper title, meta description, etc.   | Pass       |                                     |
| TC019            | Security                  | Inspect for HTTPS, input sanitization         | HTTPS not required, SQL injection not possible(no DB) | Pass       |                                     |



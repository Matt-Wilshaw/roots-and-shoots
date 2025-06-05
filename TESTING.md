#Testing

# Validation Testing using W3C

# CSS validation

CSS validation is the process of checking your CSS code to ensure it follows the official syntax rules defined by the W3C (World Wide Web Consortium). 
It helps you catch errors, improve browser compatibility, and write cleaner, more maintainable styles so that other developers can work on your code if required. - W3C

## style.css

![css validation](/testing-images/css_validation.jpg)

**Errors fixed**

- Removed unused font weight
- Removed solid is not a border-radius value : 6px solid

**Warnings not resolved**

The following 4 errors listed are out of the webdesingers control and therfore they have only been noted.

# HTML validation

HTML validation is used to check whether your HTML code follows the official standards and syntax rules defined by the W3C (World Wide Web Consortium). 
Validating your HTML helps ensure your website works correctly, is accessible, and is easier to maintain. Validating HTML also enhances search engine optimization (SEO) 
and ensures consistent display across different browsers.  - W3C

## index.html

![Validation of index.html](/testing-images/index_validation.jpg)

## plants.html

![Validation of plants.html](/testing-images/plants_validation.jpg)

Unresolved validation, changing of these suggested elements breaks the layout of the page

![Unresolved plants.html validation](/testing-images/plants_validation_unresolved.jpg)

Further research assisted with the below fix to line 345

 </section>
            </div> <!-- End of #nav-house tab pane -->
        </div> <!-- Closing tag-content -->
    </main>

## events.html

![Validation of events.html](/testing-images/events_validation.jpg)

## gallery.html

![Validation of gallery.html](/testing-images/gallery_validation.jpg)

## subscribe.html

![Validation of subscribe.html](/testing-images/subscribe_validation.jpg)

## success.html

![Validation of success.html](/testing-images/success_validation.jpg)

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

Tested using Windows Narrator, no issue found.

# Bowser Compatibility

![powerMapper](/testing-images/powerMapper.jpg)

- Edge
- Chrome
- Safari
- Firefox

## Bugs and know issues

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

![Plants text area is different heights on different screens resolution.](/testing-images/plants_scaling_resolved.jpg.jpg)

6. Modal shift page left when clicking on an image.

![Modal shift page left when clicking on an image.](/testing-images/modal_issue.jpg)

Added the following code to stop the shift of the Modal

![Modal shift page left when clicking on an image.](/testing-images/modal_issue_resolved.jpg)


**Defects Unresolved**

Subscribe.html
-You are able to put an unrealistic DOB into the field, this is outside of the scope of this project so it wont be resolved.


# User Acceptance Stories – Roots and Shoots Website

---

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
- [Done] Check color contrast for accessibility  
- [Done] Validate font consistency and layout spacing


# Week 1-3: Understanding the fundamental building blocks of web pages - accessible, semantic HTML, and well-organised CSS.
Referencing my first team project <a href="https://github.com/Paing-Ko/ecoecho">ecoecho</a> and [My Website](https://github.com/Paing-Ko/myWebsite) for FAC application in July 2023.


## 1. Structure a site using semantic HTML to aid accessibility

<img width="500" alt="Screenshot 2023-10-09 at 23 59 29" src="https://github.com/FAC29A/paing_portfolio/assets/75099079/dbb554d9-6358-4f15-a7f2-3b33140c7899">

Above screenshot shows how I used semantic HTML to improve user's accessibility.
- The `<blockquote>` element is a semantic tag used to define a section that is quoted from another source, enhancing the meaning and structure of the content.
- The `<cite>` tag gives credit to the source, providing additional contextual information and ensuring credibility.

- The `<section>` element provides a clear, semantic delineation of a content area, and it's paired with a descriptive `<h2>` heading, “Contact Us,” to convey the purpose of the section to users and assistive technologies.
  
- Within the form, we utilize the `aria-required="true"` attribute to denote obligatory fields, making form interactions more understandable for screen reader users.
  
- The use of `<input type="email">` and `placeholder` attributes not only supports input validation but also provides users with hints about the expected data format.
  
- The `<fieldset>` and `<legend>` elements are used to group related fields and provide a readable name for the group, enhancing both visual and programmatic organization of the form, which is crucial for accessible user experience.


## 2. Ensure a web page is readable for screen readers
Like always, I tried to pay attention to the convenience of screen reader users.

- **Language Specification**: Use `<html lang="en">` to aid screen reader pronunciation.


- **Semantic HTML**: Employ semantic elements (e.g., `<header>`, `<nav>`, `<section>`, etc.) to assist screen reader navigation.


- **Alternative Text for Images**: Utilize `alt` attribute (e.g., `<img alt="Description">`) for image context.


- **ARIA Labels**: Apply `aria-label` (e.g., `<nav aria-label="Main Navigation">`) to give additional context.

 
- **Skip to Content**: Possibly use anchor links (e.g., `<a href="#home">Home</a>`) to implement a "skip to content" feature.

 
- **Responsive Design**: Ensure mobile-friendliness with the meta viewport tag.

 
- **Form Accessibility**: Indicate required fields with `required` and `aria-required="true"`.


- **Keyboard Navigation**: Incorporate keyboard-navigable elements like form submission buttons.


- **Descriptive Link Text**: Offer descriptive link text (e.g., `<a href="#home">Home</a>`) for clarity of destination.


## 3. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

<img width="417" alt="Screenshot 2023-10-10 at 00 47 00" src="https://github.com/FAC29A/paing_portfolio/assets/75099079/e07a3d5b-7d34-4d88-bdef-860691f0551a">


- **Dark Text on Light Background:** Use `--text-color: #000;` on `--background-color: #f9f9f9;`.
- **High-Contrast Inverse Color:** Implement `--text-inverse-color: #fff;` for contrasting against dark.
- **Contrasting Button States:** Apply `--button-bg-color: #333;` and `--button-bg-hover-color: #555;` for feedback.
- **Explicit Color Definitions:** Define colors explicitly for consistent UI.
- **CSS Custom Properties:** Manage and adjust colors effortlessly.
- **Subtle Shadow Color:** Choose `--shadow-color: rgba(133, 190, 225, 0.927);` for a mild visual depth.

> **Note:** To ensure genuine accessibility, [Contrast Checker](https://webaim.org/resources/contrastchecker/) is used to validate colour contrast.



## 4. Use various tools to check that our website meets accessibility criteria
<img width="400" alt="Screenshot 2023-10-10 at 01 08 09" src="https://github.com/FAC29A/paing_portfolio/assets/75099079/359c081f-366b-4dca-b242-4dd17926bc96">


- **Automated Testing Tools:**
  - Used chrome [Lighthouse](https://developers.google.com/web/tools/lighthouse) for web page quality, including accessibility.
  
- **Color Contrast Checkers:**
  - [Contrast Checker](https://webaim.org/resources/contrastchecker/): Validated the contrast between text and background colors.
  
- **Screen Reader Testing:**
  - Manually tested using various screen readers like VoiceOver(macOs), Narrator(Windows 10) to validate the user experience for visually impaired users.

- **Keyboard Navigation:**
  - Verified that our website can be navigated comprehensively using keyboard inputs alone.




## 5. Use CSS media queries to ensure our content is always presented effectively on screens of different sizes
![Screenshot 2023-10-10 at 01 17 29](https://github.com/FAC29A/paing_portfolio/assets/75099079/5612d392-f206-4b89-8baa-483e8d18abd6)

### Responsive Design Implementation
- **Small Screens (≤ 768px):** To enhance readability and usability on mobile devices with CSS: `@media screen and (max-width: 768px) { ... }`
- **Medium Screens (769px - 1250px):** Optimize layouts for tablets and small desktops using: `@media screen and (min-width: 769px) and (max-width: 1250px) { ... }`
- **Toggle Mobile/Desktop Menus (≥ 769px):** Adjust menu displays for desktop screens through: `@media screen and (min-width: 769px) { ... }`


## 6. Demonstrate a mobile-first approach to building a website

![Screenshot 2023-10-10 at 01 20 47](https://github.com/FAC29A/paing_portfolio/assets/75099079/2dab365e-ee0a-40b8-baa0-9b076325c028)





## 7. Use CSS variables to apply repeated colours to HTML elements

![Screenshot 2023-10-10 at 01 22 05](https://github.com/FAC29A/paing_portfolio/assets/75099079/40a53a67-bb6b-4a06-ad38-80a76a47cca8)


## 8. Use CSS Flexbox to style children in a single-direction layout (ie a row or a column)
![Screenshot 2023-10-10 at 01 26 59](https://github.com/FAC29A/paing_portfolio/assets/75099079/3b035cb0-3f28-49d8-8917-d2e530995da0)


## 9. Use CSS Grid to style children in two-direction layout

![Screenshot 2023-10-10 at 01 30 48](https://github.com/FAC29A/paing_portfolio/assets/75099079/dc0dc0d9-4346-46db-a082-99f140884ce5)

Above screenshot is from my Website for FAC application project which uses CSS grid.

## 10. Ensure our Git commit history tells a coherent story

![Screenshot 2023-10-10 at 01 35 58](https://github.com/FAC29A/paing_portfolio/assets/75099079/2fd752a1-7448-4c46-9d97-fdd51bd213a5)

Being the first project done with another collaborator, there is a different style on committing, yet it seems like a good start.


## 11. Use the appropriate input types in HTML forms for gathering different types of information
![Screenshot 2023-10-10 at 01 37 59](https://github.com/FAC29A/paing_portfolio/assets/75099079/7d40e16d-9e49-4603-83d8-7d08edd76dba)

## HTML Forms: Using Appropriate Input Types

- **Text Input:** `<input type="text">` for gathering generic single-line text (e.g., Name).
- **Email Input:** `<input type="email">` specifically for email addresses, with built-in validation.
- **Textarea:** `<textarea>` for multi-line text inputs (e.g., Messages).
- **Radio Buttons:** `<input type="radio">` allows users to select one option from a predefined set.
- **Submit Button:** `<button type="submit">` to trigger form submission.


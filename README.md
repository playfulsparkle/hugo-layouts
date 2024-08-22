Hugo layouts
============================

This repository is a collection of Hugo layout partials for your next Hugo base project. Each partial serves a specific purpose to enhance the functionality and design of the site.

Table of Contents
-----------------

*   [Layout Partials](#layout-partials)
    *   [breadcrumb.html](#breadcrumbhtml)
    *   [gtm.html](#gtmhtml)
    *   [languagelinks.html](#languagelinkshtml)
    *   [languageswitcher.html](#languageswitcherhtml)
    *   [svgicons.html](#svgiconshtml)
    *   [toc.html](#tochtml)
*   [Usage Instructions](#usage-instructions)
*   [Contributing](#contributing)
*   [License](#license)

Layout Partials
---------------

### breadcrumb.html

This partial generates accessible breadcrumb navigation, which helps users understand their current location within the site’s hierarchy.

**Usage:**

To use this partial, include the following code in your layout files where you want the breadcrumb navigation to appear:

```go
{{ partial "breadcrumb.html" . }}
```

**Example:**

```html
<nav class="breadcrumb-nav" aria-label="Breadcrumb">
  <ol class="nav-list">
    <li><a href="/en-us/"><svg class="icon icon-home" role="img"><title>Frontpage</title><use xlink:href="#icon-home"></use></svg></a></li>
    <li><a href="/en-us/about/" aria-current="location">About</a></li>
  </ol>
</nav>
```

### gtm.html

This partial integrates Google Tag Manager (GTM) into your site. It adds GTM code to both the header and footer of the page to enable tracking and analytics.

**Usage:**

1.  Insert the GTM code snippet in the header by placing this code in your `head.html` file:

```go
{{- partial "partials/gtm/header.html" (dict "gtmID" "GTM-XXXXXXXX" ) }}
```
    

3.  Insert the GTM code snippet in the footer by placing this code in your `footer.html` file:

```go
{{ partial "partials/gtm/footer.html" (dict "gtmID" "GTM-XXXXXXXX" ) }}
```
    

Replace `"GTM-XXXXXXXX"` with your actual GTM ID.

### languagelinks.html

This partial adds `<link rel="alternate" hreflang="<language-code>" href="<url>">` tags to the page header. These tags help search engines understand the available translations of the page.

**Usage:**

Place the following code in your `head.html` file:

```go
{{ partial "languagelinks.html" . }}
```

**Example:**

```html
<link rel="alternate" hreflang="en-US" href="http://mydomain.com/en-us/">
<link rel="alternate" hreflang="x-default" href="http://mydomain.com/en-us/">
<link rel="alternate" hreflang="hu-GB" href="http://mydomain.com/en-gb/">
```

### languageswitcher.html

This partial adds an accessible language switcher to any part of the page. It lists all available translations, allowing users to easily switch between languages.

**Usage:**

To include the language switcher, use the following code where you want the switcher to appear:

```go
{{ partial "languageswitcher.html" . }}
```

**Example:**

```html
<div class="languages-switcher menu-button">
  <button type="button" id="translation-menu-XXXXXXXXXX" aria-label="Content Language Selector. Currently set to English (United States)" lang="en-US" dir="ltr" aria-haspopup="true" aria-controls="translation-list-XXXXXXXXXX" aria-expanded="false">
    <svg class="icon icon-globe" aria-hidden="true"><use xlink:href="#icon-globe"></use></svg> English (United States)
  </button>
  <ul id="translation-list-XXXXXXXXXX" role="menu" aria-labelledby="translation-menu-XXXXXXXXXX">
    <li role="none"><a href="/en-us/" lang="en-US" dir="ltr" rel="alternate" hreflang="en-US" role="menuitem" aria-current="location" tabindex="-1">English (United States)</a></li>
    <li role="none"><a href="/hu-hu/" lang="hu-HU" dir="ltr" rel="alternate" hreflang="hu-HU" role="menuitem" tabindex="-1">Magyar (Magyarország)</a></li>
  </ul>
</div>
```

### svgicons.html

This partial inserts SVG code for several icons that can be used throughout your page. SVG icons are scalable and can be styled with CSS.

**Usage:**

To include SVG icons in your page, use the following code:

```go
{{ partial "svgicons.html" . }}
```
    
### toc.html

This partial generates a Table of Contents (TOC) for HTML pages specifically. It helps users navigate the content by providing a list of headings on the page.

**Usage:**

To include the Table of Contents, use the following code where you want the TOC to appear:

```go
{{ partial "toc.html" . }}
```
    
```html
<nav class="toc-nav" aria-label="Table of Contents">
  <h3>Table of Contents <button type="button" class="toc-btn-primary" aria-controls="toc-nav-list" aria-expanded="false">
      <svg class="icon icon-arrow" aria-hidden="true">
        <use xlink:href="#icon-arrow"></use>
      </svg>
    </button></h3>
  <ul class="nav-list" id="toc-nav-list">
    <li>
      <a href="<url>#section-1">Section 1</a>
    </li>
    <li data-autohide="true" hidden>
      <a href="<url>#section-2">Section 2</a>
    </li>
  </ul>
  <button type="button" class="toc-btn-secondary" aria-controls="toc-nav-list" aria-expanded="false">
    <svg class="icon icon-dots-three-horizontal" aria-hidden="true">
      <use xlink:href="#icon-dots-three-horizontal"></use>
    </svg>
    <svg class="icon icon-arrow" aria-hidden="true">
      <use xlink:href="#icon-arrow"></use>
    </svg>
  </button>
</nav>
```


Usage Instructions
------------------

1.  **Integrate Partials:** Include the appropriate partials in your layout files (e.g., `head.html`, `footer.html`, etc.) according to the usage instructions provided above.
2.  **Customize:** Adjust the partials as needed to fit the design and functionality requirements of your site.
3.  **Test:** Ensure that all partials are correctly implemented and functioning by testing your site across different pages and devices.

Contributing
------------

Contributions to this project are welcome. To contribute:

1.  Fork the repository.
2.  Create a new branch for your changes.
3.  Make your changes and test them.
4.  Submit a pull request with a detailed description of your changes.

License
-------

This project is licensed under the [GPL-3.0 license](LICENSE).

For any questions or issues, please feel free to open an issue on the GitHub repository.
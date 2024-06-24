# Layout partials for Hugo static site generator

## Google Tag Manager

Use the following snippets to add the Google Tag Manager required code to your webpage.

**Header template snippet**

```go
{{ partial "partials/gtm/header.html" (dict "gtmID" "xxx-xxxxxxxxx" ) }}
```

**Output**

```html
  <script>(function (w, d, s, l, i) {
      w[l] = w[l] || []; w[l].push({
        'gtm.start':
          new Date().getTime(), event: 'gtm.js'
      }); var f = d.getElementsByTagName(s)[0],
        j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
          'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
    })(window, document, 'script', 'dataLayer', "xxx-xxxxxxxxx");</script>
```

**Footer template snippet**

```go
{{ partial "partials/gtm/footer.html" (dict "gtmID" "xxx-xxxxxxxxx" ) }}
```

**Output**

```html
<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=xxx-xxxxxxxxx" height="0" width="0" style="display:none; visibility:hidden;"></iframe></noscript>
```

## Language switcher

Add the following snippet to anywhere on your website to display a language switcher, it will show you all the available translations.

```go
{{ partial "languageswitcher.html" . }}
```

**Output**

```html
<ul>
    <li><a href="/hu/" rel="alternate" lang="hu" reflang="hu-HU">Magyar</a></li>
    <li><strong lang="en">English</strong></li>
</ul>
```

## Breadcrumb

Add the following snippet anywhere on your website to display an accessible breadcrumb, which helps visitors easily navigate visitors on your website.

```go
{{ partial "breadcrumb.html" . }}
```

**Output**

```html
<nav aria-label="Breadcrumb navigation">
  <ol>
    <li><a href="/en/">Frontpage</a></li>
    <li><a aria-current="page" href="/en/services/">Services</a></li>
  </ol>
</nav>
```

## Language links

Add the following snippet anywhere on your website to add `<link>` to your header for easier discovery. It supports `x-default` too.

```go
{{ partial "languagelinks.html" . }}
```

**Output**

```html
<link rel="alternate" hreflang="en-US" href="http://mywebsite.com/en/">
<link rel="alternate" hreflang="hu-HU" href="http://mywebsite.com/hu/">
<link rel="alternate" hreflang="x-default" href="http://mywebsite.com/en/">
```
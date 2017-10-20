# 前端清单
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)

**前端发布检查清单** 是在站点/HTML页面发布到生产之前，需要测试测试的所有元素的详尽列表。

它基于前端开发人员的多年经验，并附加了一些其他的开源清单。

## 目录
1. **[使用说明](#how-to-use)**
2. **[Head](#head)**
3. **[HTML](#html)**
4. **[Webfonts](#webfonts)**
5. **[CSS](#css)**
6. **[Images](#images)**
7. **[JavaScript](#javascript)**
8. **[Performance](#performance)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## How to use?
**前端清单**中的所有项目都是大多数项目所必需的，但某些元素可以省略或不重要（如果是管理Web应用程序，则可能不需要RSS提要）。 我们选择使用3级灵活性：

* ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 意味着此项是 **推荐使用**，但在某些特定情况下可以省略。
* ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 意味着该项目是 **强烈推荐**，并且最终可能在某些特殊情况下被省略。 一些元素，如果省略，可以在性能或SEO方面具有印象。
* ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 意味着 **由于任何原因不能省略**。 元素省略后您的页面可能会导致功能障碍或有可访问性或SEO问题。 测试优先级首先需要以上元素上。

以下标识不同类型资源的符号，可以帮助你理解清单上的内容。

* 📖: 文档和文章
* 🛠: 在线工具/测试工具
* 📹: 媒体或视频内容

---
## Head

> **Notes:** 你可以查看[a list of everything](https://github.com/joshbuchea/HEAD) 它列出了`<head>`中所有元素。

### Meta 标签

* [ ] **Doctype:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Doctype是HTML5所有HTML页面的顶部。

```html
<!-- Doctype HTML5 -->
<!DOCTYPE html>
```

> 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

* [ ] **X-UA-Compatible:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 存在 X-UA-Compatible 属性 meta 标签。

```html
<!-- 指示Internet Explorer使用其最新的渲染引擎 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [Specifying legacy document modes (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) viewport 声明正确。

```html
<!-- Viewport 为响应式网页 -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 标题标签应用在所有的页面 (SEO：网站页面标题不超过65个字符)

```html
<!-- 网页标题 -->
<title>网站页面标题不超过65个字符</title>
```

 📖 [Title - HTML | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

* [ ] **Description:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) meta中 提供description属性, 它是唯一的，并且要少于150字符。

```html
<!-- Meta Description -->
<meta name="description" content="描述字符少于150字">
```

* [ ] **Favicons:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 每个图标都已创建并且正确显示. 如果你只有一个 ``favicon.ico``, 放在你站点的根目录下。 通常你不需要修饰别的标记。 然而，使用下面的示例链接到可能是很好的做法。今天，推荐** PNG格式**通过``.ico``格式（尺寸：32x32像素）
```html
    <!-- 标准favicon -->
    <link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico" />
    <!-- 推荐的favicon格式 -->
    <link rel="icon" type="image/png" href="https://example.com/favicon.png" />
``` 

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](http://caniuse.com/#feat=link-icon-png)
* [ ] **Apple Touch Icon:** ![Low](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 苹果应用触摸favicon适用于苹果移动网络应用程序。*(创建您的Apple图标文件至少200x200px维度，以支持您可能需要的所有维度)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```
> * 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

* [ ] **Canonical:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 使用 ``rel="canonical"`` 来避免重复的内容

```html
<!-- 有助于防止重复的内容问题-->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

### HTML tags
* [ ] **Language tag:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 指定您网站的语言标签，与当前页面的语言相关。

```html
<body lang="en">
```
* [ ] **Direction tag:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 可以在body标签上指定文本方向 (他可以同样适用在html的其他标签上).

```html
<body dir="rtl">
```

> 📖 [dir - HTML | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 指定您网站的语言标签，并与当前页面的语言相关。

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 如果有需要，为IE提供条件注释。

> 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **CSS Critical:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) The CSS critical （或“折叠之上”） 书写用于呈现页面所有可以可见部分的写在 ``<style></style>``一行中。

> 🛠 [Critical by Addy Osmany on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png)在``<head>``中，所有CSS文件都会的所有JavaScript文件之前加载。 （除了这种情况，有时JS文件会异步加载到页面顶部）。

### Social meta
***Facebook OG*** and ***Twitter Cards*** are, 对于所有网站，强烈推荐。 其他社交媒体标签可以考虑，如果您针对特定的使用的标签，并确保显示正常。

* [ ] **Facebook Open Graph:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 所有Facebook Open Graph（OG）都经过测试，没有人丢失或虚假信息。 图片至少需要600 x 315像素，建议使用1200 x 630像素。

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)
 
* [ ] **Twitter Card:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png)

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator) 

**[⬆ back to top](#table-of-contents)**

---

## HTML

### 最佳实践
* [ ] **符合W3C的标签:**: ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有页面都需要通过W3C验证器进行测试，以避免HTML代码中出现问题。
 
> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 使用工具帮助我分析一下，我可能在我的HTML代码的任何问题。

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **桌面浏览器:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有页面都在所有当前的桌面浏览器（Safari，Firefox，Chrome，Internet Explorer，EDGE ...）上进行了测试。
* [ ] **手机浏览器:**  ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有的页面都在所有的手机浏览器上进行测试 (Native browser, Chrome, Safari...).

* [ ] **链接测试:** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 没有不可用的连接，确保你的页面没有404错误。
 
> * 🛠 [W3C Link Checker](http://validator.w3.org/checklink)

* [ ] **Adblockers测试:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 您的网站在启用广告拦截器的情况下可以正确显示的内容（您可以提供一条消息，鼓励人们停用其广告代码）

- [ ] **完美像素:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 页面接近像素完美。 根据广告素材的质量，您可能不会100％准确，但您的网页需要靠近您的模板。

>  [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ back to top](#table-of-contents)**

---
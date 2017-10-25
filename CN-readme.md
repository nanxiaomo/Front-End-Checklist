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

## Webfonts

* [ ] **Webfont格式:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有现代浏览器都支持WOFF，WOFF2和TTF。
  
> * 📖 [WOFF - Web Open Font Format - Caniuse](http://caniuse.com/#feat=woff). 
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](http://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](http://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont 尺寸:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Webfont尺寸不超过2 MO（包括所有变体）

**[⬆ back to top](#table-of-contents)**
---
## CSS

> **注意:** 大多数前端工作人员可以查看[CSS指南](https://cssguidelin.es/) 和[Sass 指南](https://sass-guidelin.es/)  如果你对css的属性具有疑问，可以查看 [CSS 参考](http://cssreference.io/).

* [ ] **响应式网页设计：** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 正在使用响应式设计的网站
* [ ] **CSS 打印样式:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png)提供打印样式表，并在每个页面上都是正确的。
* [ ] **预处理器:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 你的页面中使用预处理器 ([Sass](http://sass-lang.com/) 是首选).
* [ ] **唯一 ID:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 如果你使用ID,确保在页面中唯一存在。
* [ ] **去除基本样式 CSS:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 使用CSS重置（重置，归一化或重新设置）并进行更新。 *（如果您正在使用像Twitter Bootstrap或Foundation这样的CSS框架，则已经包含了Normalize）。*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://v4-alpha.getbootstrap.com/content/reboot/)

* [ ] **JS 前缀:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 所有类（或JavaScript文件中使用的id）以** js - **开头，不会被CSS风格化。

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS embed or line:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png)尽量避免使用CSS嵌入或内联：仅用于必须的理由（例如：对于滑块背景图像，CSS的关键）
* [ ] **供应商前缀：** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 使用CSS供应商前缀，并相应地生成您的浏览器兼容性。

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performance

- [ ] **级联:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) CSS文件连接在一个文件中 *(Not for HTTP2)*
- [ ] **压缩** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 将所有的css文件缩小。 *(Not for HTTP2)* 
- [ ] **非阻塞:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) CSS文件需要非阻塞，以防止DOM花费时间加载。

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)

- [ ] **无用的 CSS:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 移除无用的css。

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)


### CSS 测试

* [ ] **Stylelint:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有CSS或SCSS文件没有任何错误。

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **响应式网页设计：** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有页面都在以下像素进行测试：320像素，768像素，1024像素（根据您的分析，可以更多/不同）。

* [ ] **CSS验证器：** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 测试了CSS，并纠正相关的错误。

> 🛠 [CSS Validator](http://jigsaw.w3.org/css-validator/)

* [ ] **调试CSS：** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 页面使用DebugCSS进行测试

> 🛠 [Debug CSS](http://yahoo.github.io/debugCSS) (you can use the bookmarklet)

* [ ] **阅读方式：** ![High](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 如果需要支持不同的阅读方式，则需要对LTR和RTL语言进行测试。

**[⬆ 返回顶部](#table-of-contents)**

---
## 图片

> **注意:** 要完整了解图像优化，请查看免费电子书**[Essential Image Optimization](https://images.guide/)** 来自Addy Osmani.

### 最佳做法
* [ ] **优化:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有图像都经过优化，可以在浏览器中呈现。 WebP格式可用于关键页面（如首页）。

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Retina:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 您提供布局图像x2或3x，支持视网膜显示。
* [ ] **Sprite:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 小图像在一个精灵文件中（在图标的情况下，它们可以在SVG精灵图像中）。
* [ ] **宽和高:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有``<img>``设置height和width（不要指定px或％）。

> ***注意:*** 许多开发人员假设宽度和高度与响应式网页设计不兼容。 绝对不是这样。

* [ ] **替代文字:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有``<img>``有一个替代的文字，可视化地描述图像。
* [ ] **懒加载:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 图像是懒加载的（总是提供noscript后备）。
**[⬆ 返回顶部](#table-of-contents)**

---
## JavaScript

### 最佳做法

* [ ] **JavaScript内联:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 代码中没有任何内联的JavaScript代码 (混合着HTML代码).
* [ ] **级联：** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) JavaScript文件链接。
* [ ] **压缩:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) JavaScript 文件压缩 (你可以添加``.min``后缀).

> [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **非阻塞：** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) JavaScript文件使用“async”异步加载，或者使用“defer”属性延迟加载。

> 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![低](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png) 如果您需要定位一些特定功能，您可以使用自定义Modernizr在“<html>”标签中添加类。

> 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript  测试

* [ ] **ESLint:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ESLint没有标记错误（根据您的配置或标准规则）

**[⬆ 返回顶部](#table-of-contents)**

---
## 性能

### 最佳做法

- [ ] **页面宽度:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 每个页面宽度在 0ko and 500ko间

> * 🛠 [Website Page Size Online Checker](https://smallseotools.com/website-page-size-checker/)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **压缩:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 你的HTML 是压缩过的。
> 🛠 [W3C Validator](http://validator.w3.org/)
 
* [ ] **懒加载:** ![Medium](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 需要对图像、脚本和CSS进行延迟加载，以改进当前页面的响应时间。 (详见各自的章节).

### Performance testing

* [ ] **Google PageSpeed:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有页面都经过测试（不只是主页），还有最小90/100。

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ 返回顶部](#table-of-contents)**

---
## 可访问性

> **注意:** 你可以观看播放列表 [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### 最佳做法

- [ ] **渐性增强:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 主要功能如主导航和搜索应该在没有JavaScript的情况下工作。

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **色彩对比：** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 颜色对比度至少应通过WCAG (AAA for mobile)

> 🛠 [Contrast ratio](http://leaverou.github.io/contrast-ratio/)

#### 标题

* [ ] **H1:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 所有页面都有H1，且不是网站的标题。
* [ ] **标题:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 标题应以正确的顺序正确使用（H1至H6）

> 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<header>`` 有 ``role="banner"``
- [ ] **Role navigation:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<nav>`` 有 ``role="navigation"``
- [ ] **Role main:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) ``<main>`` 有 ``role="main"``

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semantic语义

- [ ] **使用特定的HTML5输入类型：** 这对于显示移动设备不同类型的自定义键盘和小部件尤其重要。

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### 表
* [ ] **Label:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 标签与每个输入表单元素相关联。 如果无法显示标签，请改用``aria-label`` 。
> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### 辅助功能测试
* [ ] **辅助功能标准测试** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 使用WAVE工具测试您的页面是否符合辅助功能标准。

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **键盘导航:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 仅以您的键盘测试您的网站，以预见的顺序。 所有交互式元素都可访问和可用。
* [ ] **屏幕阅读器：** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 所有页面都在屏幕阅读器（VoiceOver，ChromeVox，NVDA或Lynx）中进行了测试。
* [ ] **焦点样式:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) 如果焦点被禁用，它将被CSS中的可见状态所替代。

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ 返回顶部](#table-of-contents)**

---
## SEO

* [ ] **Google Analytics:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) Google Analytics（分析）已安装并正确配置。
* [ ] **标题逻辑** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 标题文字有助于了解当前页面中的内容。
* [ ] **sitemap.xml:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) sitemap.xml已存在，并已在Google Search Console中提交（例如：Google网站管理员工具）
* [ ] **robots.txt:** ![高](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png) robots.txt不阻止网页
将您的网站链接到Google网站管理员工具
* [ ] **Sitemap HTML:** ![中](http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png) 提供HTML网站地图，可通过网站页脚中的链接进行访问。

**[⬆ 返回顶部](#table-of-contents)**

---
## Contributing

**Open an issue or a pull request to suggest changes or additions.**



### Contributors

Check out all the super awesome [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Authors

**[David Dias]()**, **[Geoffrey Signorato](https://github.com/geosenna)**, **[Sandeep Ramgolam](https://twitter.com/__Sun__)** and **[Cédric Poilly](https://github.com/CedricPoilly)**.
**[王菲], 仅为中文版翻译

## License

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ 返回顶部](#table-of-contents)**








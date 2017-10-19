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

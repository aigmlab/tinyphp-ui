# TinyPHP UI

## 中文

### 简介

基于 [aigm/tinyphp](https://github.com/aigmlab/tinyphp) 的前端 UI 组件库。

项目地址: [https://github.com/aigmlab/tinyphp-ui](https://github.com/aigmlab/tinyphp-ui)

### 面向对象

- 熟练掌握 bootstrap / jquery / css / vue
- 熟悉 JavaScript
- 面向 PHP 全栈工程师
- 自定义开发需要熟悉 webpack

### 适用场景

- 管理后台开发 (ERP / CRM / SRM / OA)
- 响应式 Web 应用

### 在 tinyphp 中使用

#### Composer

```shell
composer require aigm/tinyphp-ui
```

#### NPM

```shell
npm i tinyphporg/tinyphp-ui
```

#### profile.php 配置

开启 tinyphp-ui 默认自动注入前端库:

```php
# application/config/profile.php
$profile['view']['ui']['enabled'] = TRUE;
$profile['view']['ui']['public_path'] = '/tinyphp-ui/';       // 公共访问地址
$profile['view']['ui']['inject'] = TRUE;                       // 自动注入
$profile['view']['ui']['template_plugin'] = '\\Tiny\\MVC\\View\\UI\\UIViewTemplatePlugin';
$profile['view']['ui']['helper'] = '\\Tiny\\MVC\\View\\UI\\UIViewHelper';
$profile['view']['ui']['template_dirname'] = '../vendor/aigm/tinyphp-ui/templates/';

// UI Dev 调试模式
$profile['view']['ui']['dev_enabled'] = TRUE;
$profile['view']['ui']['dev_public_path'] = "http://127.0.0.1:8080/js/tinyphp-ui.js";
$profile['plugins']['ui_dev_plugin'] = '\Tiny\MVC\View\UI\UITemplatePlugin';

// UI Installer
$profile['view']['ui']['installer']['param_name'] = 'ui-install';
$profile['view']['ui']['installer']['frontend_path'] = 'tinyphp-ui/';
$profile['view']['ui']['installer']['plugin'] = '\Tiny\MVC\View\UI\UIInstaller';
```

在视图引擎 Template 中以 tag 形式引入:

```html
{ui.lib}
<!-- 或 -->
<link href="/tinyphp-ui/css/tinyphp-ui.min.css" rel="stylesheet"/>
<script src="/tinyphp-ui/js/tinyphp-ui.min.js"></script>
```

### 前端组件库

**基础组件:**
- webpack5
- bootstrap5
- jQuery
- font-awesome
- adminlte

**可选加载库:**
- sweetalert2: 漂亮、响应式、可定制的 JavaScript 弹窗
- echarts: 基于 JavaScript 的数据可视化图表库

### 调试与自定义开发

```shell
cd vendor/aigm/tinyphp-ui
npm i
npm run dev
# 开启基于 127.0.0.1:8080 的调试 web server
```

```php
# profile.php 中检测以下配置
$profile['view']['ui']['dev_enabled'] = TRUE;
$profile['view']['ui']['dev_public_path'] = "http://front.dev.tinycn.com/js/tinyphp-ui.js";
$profile['plugins']['ui_dev_plugin'] = '\Tiny\MVC\View\UI\UITemplatePlugin';

# 在测试域名 (默认 127.0.0.1) 下访问 http://127.0.0.1/pages/index 测试
```

```shell
npm run build
# 重新打包，访问 http://127.0.0.1:8989 查看打包详情

cd tinyphp
composer post-update-cmd
# 更新到 tinyphp/public/tinyphp-ui 目录
```

---

## English

### Overview

A frontend UI component library built for [aigm/tinyphp](https://github.com/aigmlab/tinyphp).

Repository: [https://github.com/aigmlab/tinyphp-ui](https://github.com/aigmlab/tinyphp-ui)

### Target Audience

- Proficient in bootstrap / jquery / css / vue
- Strong JavaScript skills
- Full-stack PHP engineers
- Webpack knowledge required for custom development

### Use Cases

- Admin dashboard development (ERP / CRM / SRM / OA)
- Responsive web applications

### Installation

#### Composer

```shell
composer require aigm/tinyphp-ui
```

#### NPM

```shell
npm i tinyphporg/tinyphp-ui
```

### Configuration

Enable auto-injection of tinyphp-ui assets in `application/config/profile.php`:

```php
$profile['view']['ui']['enabled'] = TRUE;
$profile['view']['ui']['public_path'] = '/tinyphp-ui/';
$profile['view']['ui']['inject'] = TRUE;
$profile['view']['ui']['template_plugin'] = '\\Tiny\\MVC\\View\\UI\\UIViewTemplatePlugin';
$profile['view']['ui']['helper'] = '\\Tiny\\MVC\\View\\UI\\UIViewHelper';
$profile['view']['ui']['template_dirname'] = '../vendor/aigm/tinyphp-ui/templates/';
```

Template usage:

```html
{ui.lib}
<!-- or -->
<link href="/tinyphp-ui/css/tinyphp-ui.min.css" rel="stylesheet"/>
<script src="/tinyphp-ui/js/tinyphp-ui.min.js"></script>
```

### Component Library

**Core:**
- webpack5, bootstrap5, jQuery, font-awesome, adminlte

**Optional:**
- sweetalert2 — beautiful, responsive, customizable JavaScript popups
- echarts — JavaScript data visualization chart library

### Development

```shell
cd vendor/aigm/tinyphp-ui
npm i
npm run dev     # starts dev server at 127.0.0.1:8080
npm run build   # production build, details at 127.0.0.1:8989
```

<h1 align="center">🔐 &lt;SafeResource /&gt;</h1>

<br>

<div align="center">
  🎐 Adds CSP-compliant inline scripts and styles to Astro! 🎠
</div>

<br>
<br>

<div align="center">
  <blockquote>
    <br>
    <h4>💖 Support further development</h4>
    <span>I work hard for every project, including this one
    <br>
    and your support means a lot to me!
    <br>
    <br>
    Consider buying me a coffee. ☕
    <br>
    <strong>Thank you for supporting my efforts! 🙏😊</strong></span>
    <br>
    <br>
    <a href="https://ko-fi.com/igorskyflyer" target="_blank"><img src="https://raw.githubusercontent.com/igorskyflyer/igorskyflyer/main/assets/ko-fi.png" alt="Donate to igorskyflyer" width="150"></a>
    <br>
    <br>
    <a href="https://github.com/igorskyflyer"><em>@igorskyflyer</em></a>
    <br>
    <br>
    <br>
  </blockquote>
</div>

<br>
<br>

## 📃 Table of contents

- [Usage](#-usage)
- [Examples](#-examples)
- [Changelog](#-changelog)
- [License](#-license)
- [Related](#-related)
- [Author](#-author)

<br>
<br>

## 🕵🏼 Usage

Install it by executing:

```shell
npm i -D "@igor.dvlpr/astro-saferesource"
```

<br>

In order to use it, all you need to do is wrap your existing **inline** `script` or `style` tags with the `<SafeResource>` component, i.e.:

<br>

`before.astro`
```astro
<script is:inline>
  console.log('Hello World')
</script>
```

<br>

`after.astro`
```astro
---
import SafeResource from '@igor.dvlpr/astro-saferesource'
---

<SafeResource>
  <script is:inline> // <-- do not forget to add is:inline, if not present
    console.log('Hello World')
  </script>
</SafeResource>
```

and the component will generate the following output:

`after.html`
```astro
<!-- other page markup -->

<script integrity="sha256-xhIA8fkWcujZdN5EjKW355zTO9eHOZu4D+SzAE4Qqik=">
  console.log('Hello World')
</script>

<!-- other page markup -->
```

<br>

> [!NOTE]
> The component outputs a SHA-256 hash.
>

<br>

> [!CAUTION]
> Do **NOT** forget to add `is:inline` to the element or else Astro will remove it from the `<SafeResource>` component in order to optimize it.
>

<br>

> [!TIP]
> The component will log the ***page***, ***type*** of resource (script/style) and the generated ***hashes*** in the console of the IDE.
>

---

## ✨ Examples

`example.astro`
```astro
---
import SafeResource from '@igor.dvlpr/astro-saferesource'
import Layout from '../layouts/Layout.astro'
---

<Layout title="Welcome to Astro">
  <main style="color: wheat;">
    <SafeResource>
      <script is:inline>
        document.addEventListener('DOMContentLoaded', () => {
          const easyNav = document.getElementById('easy-nav')
          const easyShow = easyNav.getAttribute('data-show')

          if (
            easyShow === 'whenNeeded' &&
            document.documentElement.scrollHeight > window.innerHeight
          ) {
            easyNav.className = 'show'
          }
        })
      </script>
    </SafeResource>

    <SafeResource>
      <style is:inline>
        .eren-jaeger {
          color: red;
        }
      </style>
    </SafeResource>
  </main>
</Layout>
```

---

## 📝 Changelog

📑 The changelog is available here: [CHANGELOG.md](https://github.com/igorskyflyer/npm-astro-saferesource/blob/main/CHANGELOG.md).

---

## 🪪 License

Licensed under the MIT license which is available here, [MIT license](https://github.com/igorskyflyer/npm-astro-saferesource/blob/main/LICENSE).

---

## 🧬 Related

[@igor.dvlpr/astro-post-excerpt](https://www.npmjs.com/package/@igor.dvlpr/astro-post-excerpt)

> _⭐ An Astro component that renders post excerpts for your Astro blog - directly from your Markdown and MDX files. Astro v2+ collections are supported as well! 💎_

<br>

[@igor.dvlpr/astro-easynav-button](https://www.npmjs.com/package/@igor.dvlpr/astro-easynav-button)

> _🧭 Add an easy-to-use navigational button (jump to top/bottom) to your Astro site. 🔼_

<br>

[@igor.dvlpr/magic-queryselector](https://www.npmjs.com/package/@igor.dvlpr/magic-queryselector)

> _🪄 A TypeScript-types patch for querySelector/querySelectorAll, make them return types you expect them to! 🔮_

<br>

[@igor.dvlpr/zep](https://www.npmjs.com/package/@igor.dvlpr/zep)

> _🧠 Zep is a zero-dependency, efficient debounce module. ⏰_

<br>

[@igor.dvlpr/keppo](https://www.npmjs.com/package/@igor.dvlpr/keppo)

> _🎡 Parse, manage, compare and output SemVer-compatible version numbers. 🛡_

---

<br>

### 👨🏻‍💻 Author
Created by **Igor Dimitrijević** ([*@igorskyflyer*](https://github.com/igorskyflyer/)).

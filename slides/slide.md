---
marp: true
theme: uncover
_class: invert
paginate: true
transition: slide-up
style: |
  @keyframes marp-outgoing-transition-slide-up {
    from { transform: translateY(0%); }
    to { transform: translateY(calc(var(--marp-transition-direction, 1) * -100%)); }
  }
  @keyframes marp-incoming-transition-slide-up {
    from { transform: translateY(calc(var(--marp-transition-direction, 1) * 100%)); }
    to { transform: translateY(0%); }
  }
  section.danger h4 {
    color: red;
  }
  section.bullet li {
    font-size: .5rem;
  }
---

![w:160](https://playwright.dev/img/playwright-logo.svg)

# **Playwright**

> Knowledge sharing and basic code walk through

---

![bg left](https://media.tenor.com/gnXJ5j-uZdIAAAAC/migraine-headache.gif)
## Playwright ✅
<!-- _class: danger -->
#### not cypress ⛔️

---

Speed 🚀
| ![w:800](https://blog.checklyhq.com/content/images/size/w1000/2021/01/Screenshot-2021-01-26-at-18.12.23.png) |
---
| [speed comparison](https://blog.checklyhq.com/cypress-vs-selenium-vs-playwright-vs-puppeteer-speed-comparison/) |

---

Cross-Domain support 🔀
| ![w:600](https://miro.medium.com/v2/resize:fit:720/format:webp/1*4o-B0fBRghZUvJxmlSo1-w.png) |
---
| [why favor playwright](https://medium.com/tech-p7s1/why-favor-playwright-over-selenium-or-cypress-e96df84c08e1) |

---

## Flakiness 😣
<!-- _class: bullet -->
![w:800](./resources/flaky_test.png) 
- Too many (non) E2E tests
- Class name / HTML tag selectors

---

## Cannot upgrade 😓
![w:500](./resources/cypress_pr.png)
![w:500](./resources/cypress_package.png)

---

![bg fit](https://media.tenor.com/ooUIPh4oa-IAAAAC/get-out-the-lion-king.gif)

---

<!-- _class: invert -->
## 🌟 Key features 🌟

---

## Test Generator
![w:900](./resources/codegen.gif)
- Generate test in real time!

---
### Generated Code
![bg right](https://media.tenor.com/8mUWj7p8IrMAAAAC/kung-fu-panda.gif)
```ts
import { test, expect } from '@playwright/test';

test('test', async ({ page }) => {
  await page.goto('https://studio.staging.eu.next.sc/org/9/screens');
  await page.getByRole('link', { name: 'Channels' }).click();
  await page.getByText('16Zones (Test) Published16Zones').click();
  await page.getByTestId('add-content-button').click();
  await page.locator('.media-checked').first().click();
  await page.getByTestId('button-picker-action').click();
});
```
---
<!-- _class: invert -->
## Debugging
![h:550](https://user-images.githubusercontent.com/883973/108614092-8c478a80-73ac-11eb-9597-67dfce110e00.png)

---

## Reporter
```shell
$ npx playwright test --reporter=html
```
![w:800](./resources/report.png)
with build-in github action support 💖

---

## And many more!
- [Parallel](https://playwright.dev/docs/test-parallel) run test in parallel/serial for speed
- [Visual comparisons](https://playwright.dev/docs/test-snapshots) take snapshot and compare
- [Test fixtures](https://playwright.dev/docs/test-fixtures) group tests based on their meaning
- [Mock APIs](https://playwright.dev/docs/mock) mock API request / modify response

---

![bg](https://media.tenor.com/6-3HnH_boW8AAAAC/the-interview-seth-rogen.gif)


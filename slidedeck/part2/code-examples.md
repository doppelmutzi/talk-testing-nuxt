## Test Vue component (VTU)

```ts
import { mount } from '@vue/test-utils'
// Link component (SUT) uses NuxtLink internally
import Link from './Link.vue'
it('matches snapshot with global stub (VTU)', () => {
    const component = mount(Link, {
        props: { label: 'hello', target: 'example.com' },
        global: {
          stubs: { NuxtLink: { template: '<a><slot/></a>' }}
        }
    })
    expect(component.html()).toMatchSnapshot()
})
```

---

## VTU's stubbing project-wide

```ts
// vitest.setup.ts
import { config } from '@vue/test-utils'

config.global.stubs = {
  MoleculesPollChoices: true,
  AtomsSvgIcon: {
    template: '<span data-testid="svg-icon"><slot/></span>',
  },
}
```

---

## Test Vue component (NTU)

```ts
import { mountSuspended } from '@nuxt/test-utils/runtime'
// ...
it('matches snapshot (NTU)', async () => {
    const component = await mountSuspended(Link, { 
      props: {
        label: 'Home', target: '/' 
      }
    })
    // Vue Router automatically stubbed
    expect(component.html()).toMatchSnapshot()
})
```

---

## Override Test CTX

```ts
// override vitest.config.ts -> always nuxt
// @vitest-environment happy-dom
/*
// @vitest-environment nuxt | node
*/
import { mount } from '@vue/test-utils'
import HelloWorld from './HelloWorld.vue'

describe('helloWorld', () => {
  it('matches snapshot', () => {
    const component = mount(HelloWorld)
    expect(component.html()).toMatchSnapshot()
  })
})
```

---

## Nuxt CTX for Nuxt Modules

```ts
// @vitest-environment nuxt
// happy-dom ctx -> no active Pinia issue
import { mount } from '@vue/test-utils'
// no mountSuspended required -> no async/await involved
import CreateSurvey from './CreateSurvey.vue'

describe('createSurvey', () => {
  it('matches snapshot', () => {
    const component = mount(CreateSurvey)
    expect(component.html()).toMatchSnapshot()
  })
})

```

---

## Stubbing alternative

```ts
import { mockComponent, mountSuspended } 
  from '@nuxt/test-utils/runtime'
import CreateSurvey from './CreateSurvey.vue'

// alternative to VTU's global.stubs
mockComponent('~/components/molecules/PollChoices', {
  template: '<span>Mocked PollChoices component</span>',
})

it('matches snapshot', async () => {
  const component = await mountSuspended(CreateSurvey)
  expect(component.html()).toMatchSnapshot()
})
```

---

## Mock auto-imports

```ts
import { mockNuxtImport } from '@nuxt/test-utils/runtime'
// ...

mockNuxtImport('useState', () => {
  return () => 'Hans'
})

it('renders the input prefilled with the state val', () => {
    const wrapper = mount(YourName)
    const input = wrapper.get('input')
    expect(input.element.value).toBe('Hans')
})
```

---

## Regression testing of configurations

```ts
it('should return runtimeConfig of nuxt config', () => {
  const config = useRuntimeConfig()
  expect(config?.public).toEqual({
    myEnvVariable: 'initial',
  })
  expect(config).toMatchSnapshot()
})
```

---

## Smoke testing with NTU (E2E)

```ts
import { $fetch, setup } from '@nuxt/test-utils/e2e'

describe('app', async () => {
  await setup()

  it('checks availability of buttons', async () => {
    // boots the Nuxt app without browser
    const html = await $fetch('/')
    expect(html).toContain('Find a Date')
    expect(html).toContain('Conduct a Survey')
  })
})
```

---

## Headless Browser testing (Playwright)

```ts
import { createPage, setup, url } from '@nuxt/test-utils/e2e'
// ...
it('navigate to route and check name state', async () => {
    const page = await createPage()
    await page.goto(url('/'), { waitUntil: 'hydration' })
    await page.getByTestId('your-name').fill('Hans')
    // Navigate via client-side link to preserve state
    await page.getByRole('link', { 
        name: /Conduct a Survey/i }).click()
    await page.waitForURL('**/create-survey-poll')
    await page.waitForSelector('h1')
    const title = await page.textContent('h1')
    expect(title).toContain('Hey Hans, create a survey')
  })
```



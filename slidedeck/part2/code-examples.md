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
// @vitest-environment nuxt
// @vitest-environment node
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

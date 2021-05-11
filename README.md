## Headless UI Vue: Disabled Option in focus after click + arrow navigation

This is a minimal Vite + Vue 3 setup. To get setup:

```
yarn && yarn dev
```

To reproduce the issue:

### Safari

Open the ListboxOptions, click on the disabled option (Simon).

The disabled option should now be in focus.

### Chrome

Open the ListboxOptions, click on the disabled option (Simon) and then navigate up or down with the arrow keys.

The disabled option should now be in focus.

### Firefox

This issue doesn't happen in latest Firefox.

![image](https://user-images.githubusercontent.com/485747/117896117-2e6b7480-b303-11eb-8878-b4f9a7cd2f21.png)

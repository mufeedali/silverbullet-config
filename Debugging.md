---
tags:
- meta
- space-scripts
---

- Set the `selector` variable to any class, id, etc that you would like to track class changes for.
- Reload the UI using {[Debug: Reload UI]} so that the change takes effect.
- Enable the JavaScript Console in your web browser. (`F12` or `Ctrl+Shift+I` based on the browser.)
- Start tracking changes using {[Debug: Track class changes]}.
- Whenever a class change occurs, you will get a log message saying something like `DEBUG: Class attribute changed on:...`.
- If you’ve found what you were looking for, you can disable tracking using {[Debug: Stop tracking class changes]}.

```space-script
window.classChangeMonitorController = null;

silverbullet.registerCommand({name: "Debug: Track class changes"}, async () => {
  const selector = "#sb-current-page";
  const targets = document.querySelectorAll(selector);

  const observer = new MutationObserver((mutations) => {
    mutations.forEach((mutation) => {
      console.log('DEBUG: Class attribute changed on:', mutation.target, mutation.target.className);
    });
  });

  // Configuration of the observer:
  // - attributes: true means that attribute changes (e.g., class attributes) will be observed.
  // - attributeFilter: can be used to only observe specific attributes (e.g., class).
  const config = {
    attributes: true,
    attributeFilter: ['class']
  };

  targets.forEach((element) => {
    observer.observe(element, config);
  });

  window.classChangeMonitorController = {
    stopObserving: () => observer.disconnect(),
  };
});

silverbullet.registerCommand({name: "Debug: Stop tracking class changes"}, async () => {
  if (window.classChangeMonitorController) {
    window.classChangeMonitorController.stopObserving();
  }
});
```

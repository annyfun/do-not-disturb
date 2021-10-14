# do-not-disturb

> Control the macOS `Do Not Disturb` feature

Note that this package does not work inside a [sandboxed](https://developer.apple.com/app-sandboxing/) app.

**If you want to see an official API for this, please copy-paste the [following](https://github.com/feedback-assistant/reports/issues/221) into a new [Feedback Assistant](https://developer.apple.com/bug-reporting/) report, and submit it to Apple. Apple uses duplicates as an indication for how popular a request is.**

## Install

```sh
npm install @sindresorhus/do-not-disturb
```

## Usage

```js
import doNotDisturb from '@sindresorhus/do-not-disturb';

await doNotDisturb.enable();
```

## API

### doNotDisturb

All the methods return a `Promise`. You only really need to `await` them if you use multiple methods at once.

#### `.enable(): Promise<void>`

#### `.disable(): Promise<void>`

#### `.toggle(force?): Promise<void>`

##### force

Type: `boolean`

Force it to be enabled/disabled.

#### `.isEnabled(): Promise<boolean>`

#### `.on('change', listener, options): EventEmitter`

Attach an event listener that gets called when the "Do Not Disturb" state changes.

##### options

Type: `object`

###### pollInterval

Type: `number`\
Default: `3000`

Interval in milliseconds at which the polling for the `change` event is made.

#### `.off('change', listener): EventEmitter`

Remove an event listener that was attached previously.

```js
import doNotDisturb from '@sindresorhus/do-not-disturb';

const listener = status => {
	console.log(`Do Not Disturb status: ${status}`);
}

doNotDisturb.on('change', listener, {pollInterval: 100});

// …

doNotDisturb.off('change', listener);
```

## Related

- [do-not-disturb-cli](https://github.com/sindresorhus/do-not-disturb-cli) - CLI for this module
- [dark-mode](https://github.com/sindresorhus/dark-mode) - Control the macOS dark mode
- [macos-wallpaper](https://github.com/sindresorhus/macos-wallpaper) - Manage the desktop wallpaper
- [file-icon](https://github.com/sindresorhus/file-icon) - Get the icon of a file or app as a PNG image
- [app-path](https://github.com/sindresorhus/app-path) - Get the path to an app
- [More…](https://github.com/search?q=user%3Asindresorhus+language%3Aswift)

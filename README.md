# SRBPhysicalFeedbackJS

[![](https://unpkg.com/srbphysicalfeedbackjs/ressources/images/srb_logo.png)](https://www.srb.at)\
\
[![](https://img.shields.io/static/v1.svg?color=f5d410&labelColor=11215a&logoColor=ffffff&style=for-the-badge&label=srb.at&message=Blog)](https://www.srb.at/blog--events/) [![](https://img.shields.io/static/v1.svg?color=f5d410&labelColor=11215a&logoColor=ffffff&style=for-the-badge&label=srb.at&message=Products)](https://www.srb.at/produkte/) [![](https://img.shields.io/static/v1.svg?color=f5d410&labelColor=11215a&logoColor=ffffff&style=for-the-badge&label=srb.at&message=github&logo=github)](https://github.com/SRBConsultingTeam/) [![](https://img.shields.io/static/v1.svg?color=f5d410&labelColor=11215a&logoColor=ffffff&style=for-the-badge&label=NPM&message=srbphysicalfeedbackjs&logo=npm)](https://www.npmjs.com/package/srbphysicalfeedbackjs) [![](https://img.shields.io/static/v1.svg?color=f5d410&labelColor=11215a&logoColor=ffffff&style=for-the-badge&label=License&message=MIT)](LICENSE)

## Motivation

In modern web browser, there are already few ways to communicate with the user.
Classical ways are for example:

- showing a popup with relevant information
- displaying message toasts, which are small messages, displayed only for a few seconds and disappear automatically

However, we know many other types of feedback from native applications.
The haptic/physical types are particularly interesting.
One of the most common is vibrating your smartphone when you receive text messages. Last but not least, the message tone.

In pure web applications, haptic/physical feedback is rarely used. That's why we created this library. There are many business applications where providing haptic feedback would be very helpful. Vibration or sound feedback is a very good way to increase the user experience, especially in business processes where loud background noise or poor visibility of the screen impairs usability.

### Important technical background:

- The library can't vibrate devices, that have no vibration unit installed ;)
- For soundfeedback, you can use any type of speaker that the device supports ( Bluetooth speaker, headphones, ... )
- Check if your browser supports vibrating a compatible device: https://caniuse.com/vibration
- Check if your browser supports playing audio via JavaScript: https://caniuse.com/audio

## Getting started

**Initialize the SRBPhysicalFeedbackJS via the NPM CDN:**

For initializing the library via CDN, simply copy and paste the following in the index file of the HTML5 app:

```markup
<script src="https://npmcdn.com/srbphysicalfeedbackjs/src/SRBPhysicalFeedback.js"></script>
```

Or use the minified version

```markup
<script src="https://npmcdn.com/srbphysicalfeedbackjs/src/SRBPhysicalFeedback.min.js"></script>
```

**Initialize SRBPhysicalFeedbackJS via downloading the latest version:**

Download the latest minified version from [here](https://npmcdn.com/srbphysicalfeedbackjs/src/SRBPhysicalFeedback.min.js). Place that file into a directory of the app's folder structure, where it can access that file. For UI5 apps, using the index.html bootrapping, instantiate the Library like below via

```markup
<script src="/path/to/SRBPhysicalFeedback.min.js"></script>
```

For UI5 apps, not using the index.html startup logic, paste the following in the ressources section of the manifest file:

```json
"resources": { "js": [ { "uri": "path/to/SRBPhysicalFeedback.min.js" } ] }
```

**Initialize the Library temporarily via the browsers console. Just copy, paste and execute the following snippet in the browsers console:**

```js
var script = document.createElement("script");
script.type = "text/javascript";
script.src = "https://npmcdn.com/srbphysicalfeedbackjs/src/SRBPhysicalFeedback.min.js";
script.addEventListener("load", function () {
  alert("Playing sound pattern C");
  SRBPhysicalFeedback.soundFeedback("C");
  alert("Now vibrating pattern A");
  SRBPhysicalFeedback.vibrationFeedback("A");
});

document.head.appendChild(script);
```

## Documentation

> The documentation on this page is just an overview of the most relevant functions and features. Consider reading the [JSDoc page!](./SRBPhysicalFeedback_JSDOC.md)

# List of JS snippets useful on a daily basis

## One liner snippets:

here is a list of my favorite javascript snippet, most of them are one-line code but solve a lot of tasks!



### Javascript: Copy text to clipboard
If you work on an e-commerce website sooner or later you need to create a "copy promo code" component. It could be a popup, a push notification, or a simple text on your website. With this one line of code, you rocket it!

```javascript
const copyToClipboard =  (text) => navigator.clipboard.writeText(text);

// usage example
document.addEventListener('selectionchange', () => {
  copyToClipboard(window.getSelection().toString())
});
```
 
**Pay attention:** 
my usage example could be dangerous for performance. Use the function with a specific event and not for a recursive one.



### Javascript: Is focused
In a complex application or website it can be helpful to know if an element is in focus.
For example, you may want to know if your login popup is active and in focus to perform some actions on it.

Here's an easy way to do it!

```javascript
const isOnFocus =  (el) => (el === document.activeElement);

// usage example
isOnFocus(document.querySelector('#popup'))
```



### Javascript: Scroll an element into view
Do you need to create a smooth anchor for your website? You can use this one-line function to put your element smoothly on top. 

```javascript
const scrollToTop =  (el) => el.scrollIntoView( { behavior: 'smooth', block: 'start'});

// usage example
scrollToTop(document.querySelector('#mySection'))
```

In the same way but changing only the "block" you can anchor your element to the bottom!

```javascript
const scrollToBottom =  (el) => el.scrollIntoView( { behavior: 'smooth', block: 'end'});

// usage example
scrollToBottom(document.querySelector('#mySection'))
```



### Javascript: Detect device type
Do you want to know if your user is browsing your website from a mobile or desktop device? Check the navigator agent in this way.

```javascript
const detectDevice =  () => /Android|webOS|iPhone|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
  navigator.userAgent
)  ? 'Mobile' : 'Desktop'

// usage example
detectDevice()
```



### Javascript: Detect dark mode
Check if the user's preferred color scheme is in dark mode to offer them the perfect version of your website for them with this one line feature.



```javascript
const isDarkMode =  () => window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;

// usage example
isDarkMode()
```

#### Do you want to create a dark mode for your site?
look at [this repository](https://github.com/luciacenetiempo/DarkThemeToggle) where I create a dark mode toggle with very few lines of code: link), but first you might need to know if the user
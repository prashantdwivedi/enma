The self-hosted web IRC client — [thelounge.chat](https://thelounge.chat/)

---

### Docker users has not a simple method to install theme on lounge chat

Here is more simple and easy method.

1. Go to [https://draculatheme.com/](https://draculatheme.com/) and search the lounge scroll down and find **`Install manually`** and Download using the [GitHub .zip download](https://github.com/dracula/thelounge/archive/master.zip) option and unzip them.
2. Open you favourite code editor. Mine is `Visual Studio Code` and open folder which you download and find `.css` file. See below image you can see `dracula.css`. 
Open that file select all code and `copy` it.

![image-1](/assets/thelounge-image-1.png)

Launch your `thelounge` go to Setting → ✅ Advanced settings. Scroll down you see `Custom Stylesheet` and paste. No need for save it auto save as click out side that custome stylesheet box and see quick changes. Now enjoy `Dark mode` 🎉

![image-2](/assets/thelounge-image-2.png)

---

### Bonus tip

Sometimes if your irc, znc, bnc connection is not ssl secured the lounch chat show `⚠︎ alert` symbol in yellow which annoying you can hide it with below command.

```css
/* Hide Insecure Warning */
#sidebar .not-secure-tooltip {
  display: none;
}
```

---

### Custom CSS file save.

```css
/* Font

Good, legible Google webfonts for IRC: Archivo, Exo 2, Fira Sans, Heebo, IBM Plex Sans, Noto Sans, Open Sans, Roboto, Rubik, Source Sans Pro, Titillium Web, Ubuntu
*/
@import url('https://fonts.googleapis.com/css?family=Rubik:400,400i,500,700&display=swap');

/* Use system font by default (San Francisco on macOS) and Roboto as second */
body {
  font: 14px -apple-system, 'Roboto', 'Rubik', system-ui, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, sans-serif, BlinkMacSystemFont, Helvetica Neue, Arial;
  /* -moz-osx-font-smoothing: grayscale; */
  -webkit-font-smoothing: subpixel-antialiased;
  /* text-rendering: geometricPrecision; */
  text-size-adjust: none;
}

/* Hide Insecure Warning */
#sidebar .not-secure-tooltip {
  display: none;
}

/* General vars */
:root {
  --body-color: rgba(248, 248, 242, .77);
  --msg-self-color: #fff;
  --msg-self-bg-color: #1b1f27;
  --msg-action-color: #f1fa8c;
  --border-color: rgba(98, 114, 164, .14);
  --body-color-muted: #6272a4;
  --body-bg-color: #151320;
  --button-color: #50fa7b;
  --button-text-color-hover: #282a36;
  --overlay-bg-color: rgba(0, 0, 0, 0.5);
  --link-color: #f8f8f2;
  --window-bg-color: #282a36;
  --window-heading-color: #44475a;
  --date-marker-color: rgba(40, 42, 54, 0.5);
  --unread-marker-color: #ff79c6;
  --highlight-bg-color: rgba(255, 255, 255, .04);
  --highlight-border-color: rgba(255, 255, 255, .04);
  --upload-progressbar-color: #50fa7b;
  --highlight-msg-color: #fff;
  --time-color: rgba(255, 255, 255, .1);
  --time-color-hover: rgba(255, 255, 255, .8);
  --channel-list-item-hover-background: rgba(255, 255, 255, .05);
  --font-size: 15px;
  --font-size-msg: 15px;
  --font-size-channel-list: 15px;
  --font-weight-msg: 300;
  --font-weight-user: 500;
}

.from .user {
  font-weight: var(--font-weight-user);
}

.channel-list-item .add-channel:before {
  font-family: -apple-system, system-ui, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, sans-serif, BlinkMacSystemFont, Helvetica Neue, Arial;
  font-size: 19px;
}

/* .from .user::before {
  content: '<';
}

.from .user::after {
  content: '>';
} */

/* Mobile vars */
@media (max-width: 500px) {
  :root {
    --font-size: 16px;
    --font-size-msg: 16px;
    --font-size-channel-list: 16px;
  }
}

/* Spacings */
#loading .window {
  margin: 5px;
}

#viewport {
  padding: 0;
}

#viewport.menu-open {
  padding-left: 0;
}

.window {
  border-radius: 5px;
  box-shadow: 0 0 25px rgba(0, 0, 0, .5);
}

@media (max-width: 768px) {
  #loading .window {
    margin: 0;
  }

  #viewport,
  #viewport.menu-open {
    padding: 0;
  }

  #footer .icon {
    border-radius: 0;
  }

  .window {
    border-radius: 0;
  }
}

#chat .time {
  color: var(--time-color);
  font-size: 14px;
  font-weight: 300;
  opacity: 1;
  order: 8;
  transition: all .55s;
}

#chat .time:hover,
#chat .time:focus {
  color: var(--time-color-hover);
  opacity: 1;
}

.messages .msg {
  font-size: var(--font-size-msg);
  font-weight: var(--font-weight-msg);
  line-height: 1.45;
}

@media (max-width: 500px) {
  .messages .msg {
    line-height: 1.4;
  }
}

@media (min-width: 480px) {
  #chat .from {
    padding-left: 20px;
    width: 144px;
  }
}

/* Styles */
.messages .msg,
textarea,
input {
  font-size: var(--font-size-msg) !important;
}

.channel-list-item.active,
.channel-list-item {
  background: transparent;
}

.channel-list-item:hover,
.channel-list-item:focus {
  background: var(--channel-list-item-hover-background);
  transition: all .55s;
}

#chat .msg.self {
  /* background: var(--msg-self-bg-color); */
}

#chat .msg.self .content {
  color: var(--msg-self-color);
}

#chat .msg.self .content * {
  color: var(--msg-self-color) !important;
}

#chat .msg[data-type=action] .from::before,
#chat .msg[data-type="action"],
#chat .msg[data-type="action"] .content,
#chat .msg[data-type="action"] span,
#chat .msg[data-type="action"].self .user {
  color: var(--msg-action-color) !important;
}

@media (max-width: 479px) {
  #chat .condensed-summary .from,
  #chat .condensed-summary .time {
    display: block !important;
  }

  #chat .msg:not(.closed):not([data-type=condensed]),
  #chat .msg:not(.closed):not([data-type=condensed])[data-type="message"] {
    display: flex;
  }

  #chat .msg.closed[data-type=condensed] .msg {
    display: none !important;
  }

  #chat .time {
    overflow: visible;
    white-space: nowrap;
    width: auto !important;
  }

  #chat .from {
    flex: 0 0 auto;
    -webkit-mask-image: linear-gradient(270deg, transparent, var(--window-bg-color) 10px) !important;
    mask-image: linear-gradient(270deg, transparent, var(--window-bg-color) 10px) !important;
    padding: 2px 10px 0 0 !important;
    width: 75px !important;
  }

  #chat .content {
    border-left: 1px solid var(--body-color-muted) !important;
    flex: 1 1 auto !important;
    min-width: 0 !important;
    overflow: hidden !important;
    padding: 2px 6px 2px 10px !important;
    text-align: left !important;
  }
}

#chat .content,
#chat .header,
#chat .userlist,
#form,
#windows #form .input {
  border-color: var(--border-color) !important;
}

#chat .userlist .search,
#form {
  background: var(--window-bg-color);
}

#chat .count::before,
#chat .userlist .search::placeholder,
#form #input::placeholder {
  color: var(--body-color-muted) !important;
}

.channel-list-item[data-type=channel]::before,
.context-menu-chan::before {
  content: "\f086";
}

#sidebar {
  border-right: 1px solid var(--border-color);
  width: 180px;
}

/* Hide Insecure Warning */
#sidebar .not-secure-tooltip {
  display: none;
}

@media (min-width: 770px) {
  .channel-list-item::before {
    line-height: 18px;
    margin-right: 12px;
    width: 15px;
  }
}

#sidebar .empty,
.channel-list-item {
  font-size: var(--font-size-channel-list);
}

/* Hide Insecure Warning */
#sidebar .not-secure-tooltip {
  display: none;
}

@media (min-width: 600px) {
  .channel-list-item {
    padding: 8px 14px;
  }
}

.jump-to-input {
  display: none;
}

.logo-container {
  height: 0 !important;
  margin-top: -7px !important;
  opacity: 0 !important;
}

.networks {
  margin-top: 10px;
}

.channel-list-item[data-type=lobby],
.irc-bold,
#chat .toggle-content .head {
  font-weight: 500;
}

#chat.colored-nicks .user.color-31,
#chat.colored-nicks .user.color-5 {
  color: #40407a;
}

#chat button.menu,
#viewport .lt,
#viewport .rt {
  margin-top: 4px;
}

#chat.colored-nicks .user.color-1 {
  color: #f7adf7;
}

#chat.colored-nicks .user.color-2 {
  color: #abf99f;
}

#chat.colored-nicks .user.color-3 {
  color: #86efdc;
}

#chat.colored-nicks .user.color-4 {
  color: #b76ee5;
}

#chat.colored-nicks .user.color-5 {
  color: #f9a4b3;
}

#chat.colored-nicks .user.color-6 {
  color: #f7999a;
}

#chat.colored-nicks .user.color-7 {
  color: #f497b9;
}

#chat.colored-nicks .user.color-8 {
  color: #f9a9d7;
}

#chat.colored-nicks .user.color-9 {
  color: #7fa2e2;
}

#chat.colored-nicks .user.color-10 {
  color: #8be9fd;
}

#chat.colored-nicks .user.color-11 {
  color: #ad88fc;
}

#chat.colored-nicks .user.color-12 {
  color: #f4aead;
}

#chat.colored-nicks .user.color-13 {
  color: #fc71ab;
}

#chat.colored-nicks .user.color-14 {
  color: #ff79c6;
}

#chat.colored-nicks .user.color-15 {
  color: #8cb6ea;
}

#chat.colored-nicks .user.color-16 {
  color: #ffb86c;
}

#chat.colored-nicks .user.color-17 {
  color: #ed9b82;
}

#chat.colored-nicks .user.color-18 {
  color: #8df484;
}

#chat.colored-nicks .user.color-19 {
  color: #ffcce3;
}

#chat.colored-nicks .user.color-20 {
  color: #efcc81;
}

#chat.colored-nicks .user.color-21 {
  color: #90a1ed;
}

#chat.colored-nicks .user.color-22 {
  color: #f4d484;
}

#chat.colored-nicks .user.color-23 {
  color: #97ea70;
}

#chat.colored-nicks .user.color-24 {
  color: #fcbbba;
}

#chat.colored-nicks .user.color-25 {
  color: #eef975;
}

#chat.colored-nicks .user.color-26 {
  color: #c7ff93;
}

#chat.colored-nicks .user.color-27 {
  color: #ffade1;
}

#chat.colored-nicks .user.color-28 {
  color: #98ecf2;
}

#chat.colored-nicks .user.color-29 {
  color: #7187f2;
}

#chat.colored-nicks .user.color-30 {
  color: #9676e2;
}

#chat.colored-nicks .user.color-31 {
  color: #f2a4eb;
}

#chat.colored-nicks .user.color-32 {
  color: #85f27d;
}

#chat .unread-marker-text::before {
  background: var(--window-bg-color);
}

#chat .date-marker::before {
  border-color: #97ea70;
}

#chat .date-marker-text::before {
  background: var(--window-bg-color);
  color: #97ea70;
}

#form {
  background: var(--window-bg-color);
}

#windows #form .input {
  background-color: var(--window-bg-color) !important;
  color: #eee;
}

#form #nick {
  background: #182533;
  color: var(--body-color);
}

#form #submit:hover,
#form #submit:focus {
  opacity: 1;
}

code,
.irc-monospace {
  background: var(--window-bg-color);
  color: #f3f3f3;
}

kbd {
  background-color: #333;
  background-image: linear-gradient(rgba(0, 0, 0, .25), transparent);
  border-color: var(--window-bg-color);
  box-shadow: 0 2px 0 var(--window-bg-color), inset 0 1px 1px #777, inset 0 -1px 3px #222;
  color: #eee;
  text-shadow: 0 -1px 0 var(--window-bg-color);
}

/* Embeds */
#chat .toggle-content {
  background: var(--highlight-bg-color);
  color: #f3f3f3;
}

#chat .toggle-content .body {
  color: #99a2b4;
}

/* Form elements */

#chat-container ::placeholder {
  color: #99a2b4;
  opacity: .5;
}

#chat-container ::input-placeholder {
  color: #99a2b4;
  opacity: .5;
}

#chat-container :input-placeholder {
  color: #99a2b4;
  opacity: .5;
}

.window {
  box-shadow: none;
}

#chat .error,
#chat .error .from,
#chat .channel .highlight,
#chat .channel .highlight .from,
#chat .channel .highlight .text {
  color: #f92772 !important;
}

#chat .chat-view[data-type=channel] .msg.highlight {
  background: var(--highlight-bg-color) !important;
  border-left: 0 !important;
}

#chat .chat-view[data-type=channel] .msg.highlight .content {
  color: var(--highlight-msg-color);
  font-weight: 600;
}

body #chat .toggle-content .thumb {
  height: 100%;
  max-height: 100%;
  max-width: 100%;
  min-width: 90px;
  object-fit: cover;
  width: 90px;
}

#chat .toggle-content {
  align-items: center;
  border-radius: 5px;
  box-shadow: none;
  margin-bottom: 3px;
  margin-top: 7px;
  max-width: 100%;
  overflow: hidden;
  white-space: normal;
}

#chat .toggle-content .toggle-thumbnail {
  height: 100%;
  max-height: 68px;
}

#chat .toggle-content.opened {
  align-items: flex-start;
}

#chat .toggle-content .toggle-text {
  font-size: 15px;
  padding: 11px 15px;
}

@media (max-width: 500px) {
  #chat .toggle-content .toggle-text {
    font-size: 14px;
    padding: 8px 10px;
  }

  #form #submit,
  #form #upload {
    font-size: 18px;
  }
}

#context-menu,
.textcomplete-menu {
  background: var(--body-bg-color);
}

.context-menu-item,
.textcomplete-item {
  color: var(--body-color);
}

.context-menu-item:hover,
.textcomplete-item:hover,
.context-menu-item:focus,
.textcomplete-item:focus {
  background: rgba(255, 255, 255, .11);
}

#form #input {
  max-height: 19px !important;
  overflow-x: none !important;
  overflow-y: auto !important;
}

.textcomplete-item a {
  color: var(--body-color-muted) !important;
}

.textcomplete-item a:hover,
.textcomplete-item a:focus {
  color: var(--body-color) !important;
}

.window h2,
.window h3 {
  color: var(--body-color);
}

#chat .msg[data-type=condensed] .msg,
#chat .msg {
  padding-bottom: 0;
  padding-top: 0;
}

#chat .from::after,
#chat .from::after {
  display: none !important;
}

@media (max-width: 479px) {
  #chat .chat-view[data-type=channel] .msg.highlight {
    padding-left: 10px;
  }
}

/* General improvements moved from Custom stylesheet */
#chat .userlist {
  width: 150px;
}

/* Disable highlighted words in between text */
#chat .content span[class*="irc-"] {
  background-color: inherit;
  color: inherit;
  font-family: inherit;
  font-style: inherit;
  font-weight: inherit;
  text-decoration: inherit;
}

/* Disable highlighted words in between text */
#chat.colored-nicks .content .user[data-name] {
  color: inherit !important;
}
```
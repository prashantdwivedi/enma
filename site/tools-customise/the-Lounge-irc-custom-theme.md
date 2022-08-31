The self-hosted web IRC client — [thelounge.chat](https://thelounge.chat/)

---

### Docker users has not a simple method to install theme on lounge chat

Here is more simple and easy method.

1. Go to [https://draculatheme.com/](https://draculatheme.com/) and search the lounge scroll down and find **`Install manually`** and Download using the [GitHub .zip download](https://github.com/dracula/thelounge/archive/master.zip) option and unzip them.
2. Open you favourite code editor. Mine is `Visual Studio Code` and open folder which you download and find `.css` file. See below image you can see `dracula.css`. 
Open that file select all code and `copy` it.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4d04be9a-e1df-4ffc-bb88-6e32b1ba2581/Untitled.png)

1. Launch your `thelounge` go to Setting → ✅ Advanced settings. Scroll down you see `Custom Stylesheet` and paste. No need for save it auto save as click out side that custome stylesheet box and see quick changes. Now enjoy `Dark mode` 🎉

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e67b2f05-0dfd-4481-bfb4-907668aa46b1/Untitled.png)

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
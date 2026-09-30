# MarkPadPro Support

MarkPadPro is a fully local Markdown viewer and editor for Windows by Technocrux (Devride, https://www.devride.com).

## Make MarkPadPro your default .md app

Use any one of these:

- **In the app:** open Settings (Ctrl+,) and choose **Make default…**. The Windows Default apps page opens. Set MarkPadPro for `.md` (and `.markdown`, `.mdown`, `.mkd` if you use them).
- **From a file:** right-click a `.md` file, choose **Open with → Choose another app**, select **MarkPadPro**, then choose **Always**.
- **In Windows Settings:** go to **Settings → Apps → Default apps**, search for `.md`, and pick MarkPadPro.

The welcome tour on first launch also offers this step.

## Where settings live

MarkPadPro stores its settings, recent files list and open tabs only on your PC, in its app data folder:

```
%LOCALAPPDATA%\Packages\65490Technocrux.MarkPadPro_<id>\LocalState
```

To find it, paste `%LOCALAPPDATA%\Packages` into the File Explorer address bar and open the folder that starts with `65490Technocrux.MarkPadPro`. Your documents are never stored there. They stay wherever you saved them.

## Reset the app

Resetting deletes MarkPadPro's settings, recent files list and saved tabs. Your documents are not affected.

1. Close MarkPadPro.
2. Go to **Settings → Apps → Installed apps**, find **MarkPadPro**, select **… → Advanced options**.
3. Select **Reset**.

Or, with the app closed, delete the contents of the `LocalState` folder shown above. The welcome tour will appear again on the next launch.

To clear only the recent files list, use **Clear list** on the start screen or **Clear recent files** in the File menu.

## Common questions

- **Does it need the internet?** No. It only goes online to load images that a document itself links to on the web. Links open in your browser when you click them.
- **Where do pasted images go?** Into an `images` folder next to your document. Save the document first.
- **A file changed outside the app.** MarkPadPro reloads it automatically. If you have unsaved edits, it asks first.

## Contact

Email **alisufyanbutt@hotmail.com**. Please include your Windows version, the MarkPadPro version (shown in the Microsoft Store), and a sample `.md` file if a document renders incorrectly.

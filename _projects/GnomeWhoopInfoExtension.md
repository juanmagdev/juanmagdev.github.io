---
layout: page
title: GNOME Whoop Info Extension
description: GNOME Shell extension to display your daily WHOOP health metrics (recovery, sleep, strain) directly in the top bar.
img: assets/img/gnome-whoop-info/gnome-whoop-info-portada.jpg
importance: 2
category: fun
---

<div class="row mt-3">
    <div class="col-12 d-flex justify-content-center">
        {% include figure.liquid loading="eager" path="assets/img/gnome-whoop-info/image.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row mt-2">
    <div class="col-8 offset-2 d-flex justify-content-center">
        {% include figure.liquid loading="eager" path="assets/img/gnome-whoop-info/image-2.png" class="img-fluid rounded" style="max-width:400px;" %}
    </div>
</div>

**GNOME Whoop Info** is a lightweight GNOME Shell extension that connects to your [WHOOP](https://www.whoop.com/) account and displays your most important daily health metrics directly in the top bar of your GNOME desktop.

With this extension, you can quickly check your **recovery**, **sleep**, and **strain** status without needing to check your phone.

You can find the source code in my [GitHub repository](https://github.com/juanmagdev/gnome-whoop-extension).

---

## Features

- **WHOOP Metrics in Top Bar**: See your daily recovery, sleep, and strain at a glance.
- **Automatic Updates**: The extension updates your metrics automatically throughout the day.
- **Easy Authentication**: Authenticate securely with your WHOOP account using a simple setup process.
- **Command Line Support**: Optionally authenticate via the command line for advanced users.

## Instalation and Authentication

### 1. Clone the repository and move it to the extensions folder

```bash
git clone https://github.com/juanmagdev/gnome-whoop-extension.git
mv gnome-whoop-extension ~/.local/share/gnome-shell/extensions/whoop-info@juanmag.dev
```

Before the extension can display your WHOOP data, you must authenticate your account and generate the required access tokens.

### 2. Create a Developer App on WHOOP

- Visit the [WHOOP Developer Portal](https://developer.whoop.com/).
- Log in with your WHOOP account.
- Click **"Create an App"** and fill out the form as follows:

  | Field              | Value                            |
  | ------------------ | -------------------------------- |
  | **App Name**       | GNOME                            |
  | **Contact Email**  | your@email.com                   |
  | **Privacy Policy** | https://whoop.com                |
  | **Redirect URI**   | `http://localhost:8000/callback` |
  | **Scopes**         | Select **all** available scopes  |
  | **Webhook URL**    | (Leave empty)                    |

- After creating the app, you'll receive your **Client ID** and **Client Secret**.

### 3. Configure Authentication in the Extension

- Open GNOME Extensions app or go to Settings > Extensions.
- Find "Whoop Info" and click on the settings icon (⚙️).
- Enter your **Client ID** and **Client Secret**.
- Click **"Start Authentication"** and follow the instructions to authorize the extension.
- Paste the callback URL when prompted and complete the process.

### 4. Alternative: Command Line Authentication

- Open a terminal and navigate to the extension folder:
  ```bash
  cd ~/.local/share/gnome-shell/extensions/whoop-info@juanmag.dev
  ```
- Run the authentication script:
  ```bash
  ./whoopauth.sh
  ```
- Follow the prompts to complete the authorization.

## Screenshots

<div class="row mt-3">
    <div class="col-12 d-flex justify-content-center">
        {% include figure.liquid loading="eager" path="assets/img/gnome-whoop-info/image-3.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row mt-3">
    <div class="col-12 d-flex justify-content-center">
        {% include figure.liquid loading="eager" path="assets/img/gnome-whoop-info/image-4.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Important considerations

- **Authentication Required**: You must authenticate with WHOOP before metrics are displayed.
- **Internet Connection**: The extension requires an active internet connection to fetch data.

## Credits

- Thanks to the [WHOOP Developer Portal](https://developer.whoop.com/) for providing the API.
- Inspired by the need for quick access to health metrics on Linux desktops.

## Contributing

Feel free to open issues or submit pull requests on [GitHub](https://github.com/juanmagdev/gnome-whoop-extension) if you want to contribute or report bugs.

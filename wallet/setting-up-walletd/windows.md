---
cover: ../../.gitbook/assets/sia-banner-expanded-walletd.png
coverY: 96.98442367601245
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Windows

This guide will walk you through setting up `walletd` on Windows. At the end of this guide, you should have:

* **Installed Sia `walletd` software:** Successfully installed the Sia `walletd` software on your Windows system with the appropriate binary.
* **Created a `walletd` wallet**: created a wallet with a Seed to store your Siacoins in `walletd`.

## Pre-requisites

* **Network Access:** `walletd` interacts with the Sia network, so you need a stable internet connection and open network access to connect to the Sia blockchain.
* **Operating System Compatibility:** Ensure your Windows version is compatible with the walletd software. Check [releases](../../miscellaneous/releases.md) supported by Windows versions.
* **System Updates:** Ensure that your Windows is up to date with the latest system updates, as these updates can contain important security fixes and improvements.

## Getting `walletd`

{% hint style="info" %}
You may need to run this step in administrative mode, so right-click Command Prompt and select **Run as administrator**.
{% endhint %}

1. Download the latest version of `walletd` for your operating system from the [official website](https://sia.tech/software/renterd). For this guide, we'll be downloading the Windows version of `walletd` .
2. Now that we have downloaded `walletd`, you may need to unzip it and move it to a more accessible location:
   * Right-click the downloaded `walletd` zip file and select **Extract All** to unzip it if it hasn't done so automatically. Select an accessible destination to extract the file.
   * Click on the newly unzipped directory.
   * Open the Command Prompt
3. In the Command Prompt, move the `walletd` binary to `C:\Windows\System32` by first typing `move`, copy and paste the path of `walletd.exe` , and appending the location to where this is being moved. The command line should look something like this:

```bash
move "C:\path\to\your\unzipped\directory\walletd.exe" C:\Windows\System32
```

<figure><img src="../../.gitbook/assets/Moving walletd binary.png" alt=""><figcaption><p>Moving walletd binary</p></figcaption></figure>

4. Finally, for good practice, create a folder on the home drive. This folder will be utilized specifically to store data related to the `walletd` software.

```bash
mkdir C:\Users\<your_username>\walletd
```

## Running `walletd`

1. Run the following in your terminal command to start `walletd`:

```bash
 walletd
```

You will be prompted to input a `API password`. You choose this password, which can be anything you want. It will be used to unlock the `walletd` UI, via your browser, should be something secure and easy to remember. This value is not stored anywhere; you will need to re-enter it every time you start `walletd`.

{% hint style="info" %}
You can also set the SIA`_API_PASSWORD` environment variables so you do not have to re-enter the values every time.
{% endhint %}

2. After entering your desired `API password` and the created `seed`, `walletd` will start.&#x20;

<figure><img src="../../.gitbook/assets/Starting walletd (1).png" alt=""><figcaption><p>Starting walletd</p></figcaption></figure>

3. &#x20;You can now access the `walletd` UI by opening a browser and going to `http://localhost:9980`.&#x20;

{% hint style="warning" %}
Remember to leave the terminal window open while `walletd` it is running. If you close the command prompt window, `walletd` stop.
{% endhint %}

<figure><img src="../../.gitbook/assets/walletd Login UI.png" alt=""><figcaption><p>walletd Login UI</p></figcaption></figure>

Enter your `API password` you created in the in the previous step to unlock `walletd`.

{% hint style="success" %}
Congratulations on successfully setting up `walletd` and taking a significant step towards renting storage space on the Sia network.
{% endhint %}

## Updating

It is essential to keep your host up to date. New versions of `walletd` are released regularly and contain bug fixes and performance improvements.

To update:

1. Download the latest version of `walletd` from the [official website](https://sia.tech/software/renterd).
2. Stop the `walletd` service with the command `sc stop walletd`.
3. Unzip and replace `walletd` in `C:\Windows\System32` with the new version.
4. Restart `renterd`.
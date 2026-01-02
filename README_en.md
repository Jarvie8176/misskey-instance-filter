[中文](./README.md) | [English](./README_en.md) | [日本語](./README_jp.md)

---

# Misskey Timeline Instance Filter

This is a browser userscript designed for Misskey. It allows you to view content only from instances (servers) you are interested in when browsing the Global Timeline (GTL) or Social Timeline (STL).

If you feel there is too much irrelevant noise on the timeline and only want to focus on discussions from specific circles, this script will be very useful. It works via a "Whitelist" system, where
only content from instances on the list will be displayed.

> **Suggestion for Privacy-Conscious Users** ([Privacy Note](#privacy)):
> If you do not wish for the script to run on all websites, you can manually modify the "User Matches" in your script manager (Tampermonkey) settings to the specific Misskey instance domains you
> frequent. However, this will cause the script to lose the ability to automatically identify new instances.

## ✨ Key Features

* **Instance Whitelist Filtering**: Only content from instances you manually add to the list will be displayed.
* **Hide Local Content**: Provides an independent switch to hide posts from the current instance, allowing you to focus on exploring external instances.
* **Smart Auto-Pagination**: When an entire page of content is filtered out, the script automatically loads the next page until it finds posts that match your criteria or reaches the set limit (up to
  10 pages), saving you from the hassle of manual scrolling.
* **Recent Blocked List & Real-time Interaction**:
    * The script automatically records instance domains that were recently blocked.
* **Real-time Feedback**: When you type a domain into the whitelist edit box, the blocked list below refreshes in real-time, automatically removing domains that have just been added to the whitelist.
* **Wildcard Search**: Supports using the `*` wildcard (e.g., `*.jp`) in the "Recent Blocked List" to quickly locate instances with specific suffixes.
* **Multi-language Support**: The interface supports Simplified Chinese, Japanese, and English, and automatically detects your browser language.
* **Lightweight Design**: Runs only when a Misskey instance is detected, without consuming excess system resources.

## 🔧 Installation

1. **Install a Userscript Manager**: [Tampermonkey](https://www.tampermonkey.net/) is recommended.
2. **Install the Script**:

> **[Click here to install from GreasyFork](https://greasyfork.org/en/scripts/561182-misskey-timeline-instance-filter)**

3. **Refresh the Page**: After installation, open any Misskey instance. A **⚙️** floating button will appear in the bottom right corner.

## ⚙️ Options Explained

* **Instance Whitelist**: Enter one domain per line (e.g., `misskey.io`).
* **Recently Blocked Instances**: Shows sources that were recently hidden. Click **"Add +"** to quickly add that instance to your whitelist.
* **Hide Local Content**:
    * **Off (Default)**: Shows content from the current instance + whitelist instances.
    * **On**: Hides all local posts, displaying only remote content from the whitelist.
* **Auto-Pagination Limit**: Set the maximum number of pages the script will automatically fetch continuously when content is sparse (0-10).
* **Debug Mode**: When enabled, detailed filtering logs can be viewed in the browser console (F12).

<a name="privacy"></a>

## 🛡️ Permissions & Privacy

### Why is "Access to all websites" permission required?

Since Misskey instances are distributed across thousands of different domains, the script needs to check the `meta` tags in the webpage header to confirm if the current site is running Misskey.

1. **Silent Detection**: The script checks only once when the page loads. If the current site is not Misskey, the script stops running immediately and completely.
2. **Zero Data Upload**: All filtering logic and whitelist data are stored locally in your browser (`GM_setValue`). Your browsing history or personal information is **never** uploaded to any server.
3. **Fully Open Source**: You can view and audit every line of source code on GitHub at any time.

## 🔗 Project Links

If you find this script helpful, you are welcome to support it in the following ways:

* **Project Homepage**: [📦 GitHub Repository](https://github.com/Jarvie8176/misskey-instance-filter)
* **Feedback**: [🐛 Submit an Issue](https://github.com/Jarvie8176/misskey-instance-filter/issues)
* **Support the Author**: [☕ Buy me a coffee on Ko-fi](https://ko-fi.com/jk433552)

## ❓ FAQ

**Q: What is an "Instance"?**
A: Misskey is a decentralized social network composed of many independent servers (websites). These servers are called "instances." Users can register on different instances, but they can communicate
with each other. The Global Timeline (GTL) displays public posts from different instances.

**Q: Will this script affect posts from people I follow?**
A: No. This script primarily affects the Global Timeline (GTL) and Social Timeline (STL). It does not filter your Home Timeline (HTL), lists, or content seen when directly visiting a user's profile
page.

**Q: I added a whitelist, but the timeline seems empty/slow?**
A: This is normal because the script has filtered out all content from instances not on your whitelist. If you feel there is too little content, try using the "Recently Blocked Instances" feature to
discover and add more instances you are interested in.

**Q: Can I temporarily disable this script?**
A: Yes. You can find the installed script list in the Tampermonkey extension menu of your browser, where you can temporarily toggle off "Misskey Timeline Instance Filter."

---

*License: [MIT*](https://github.com/Jarvie8176/misskey-instance-filter/blob/main/LICENSE)

# Ad Blocker - MJB

## Overview

Ad Blocker - MJB is a Chrome extension designed to block unwanted ads and trackers by leveraging the `declarativeNetRequest` API provided by Chrome's Manifest V3. It uses a set of predefined rules to block requests to known ad-serving domains, ensuring a cleaner and faster browsing experience.

## Features

- Blocks ads from popular ad-serving domains such as `doubleclick.net`, `googleadservices.com`, and `googlesyndication.com`.
- Utilizes Chrome's efficient `declarativeNetRequest` API for performance and security.
- Easy to configure and extend by modifying the `rules.json` file.

## Project Structure

- **manifest.json**: Defines the extension's metadata and permissions.
- **rules.json**: Contains the list of blocking rules for ad-serving domains.
- **_metadata/**: Reserved for generated files by Chrome's extension system.

## How It Works

1. The `manifest.json` file specifies the use of the `declarativeNetRequest` API and points to the `rules.json` file as the source of blocking rules.
2. The `rules.json` file contains a list of rules, each specifying a URL pattern to block.
3. When the extension is loaded in Chrome, the rules are applied to block requests matching the specified patterns.

## Installation

1. Clone or download this repository.
2. Open Chrome and navigate to `chrome://extensions/`.
3. Enable "Developer mode" in the top-right corner.
4. Click "Load unpacked" and select the project folder.
5. The extension will be loaded, and ads matching the rules will be blocked.

## Customization

To add or modify blocking rules:

1. Open the `rules.json` file.
2. Add a new rule object with the desired `id`, `priority`, `action`, and `condition`.
3. Save the file and reload the extension in Chrome.

## Example Rule

```json
{
    "id": 8,
    "priority": 1,
    "action": { "type": "block" },
    "condition": { "urlFilter": "*://*example-ad-domain.com/*" }
}
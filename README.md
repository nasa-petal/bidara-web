## <img src="https://github.com/nasa-petal/discord_bot/assets/1322063/c34b5526-7186-43fc-b00a-597ee773ca7b" width="40" align="left"/> BIDARA : Bio-Inspired Design and Research Assistant
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/nasa-petal/bidara-web/pages.yml?style=flat-square)](https://github.com/nasa-petal/bidara-web/actions/workflows/pages.yml)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg?style=flat-square)](https://standardjs.com)
[![GitHub](https://img.shields.io/github/license/nasa-petal/bidara-web)](/LICENSE)
[![All Contributors](https://img.shields.io/github/all-contributors/nasa-petal/bidara-web?color=ee8449&style=flat-square)](#contributors)

### **URL**: https://nasa-petal.github.io/bidara-web/

### BIDARA is a GPT-4 chatbot that was instructed to help scientists and engineers understand, learn from, and emulate the strategies used by living things to create sustainable designs and technologies.

BIDARA can guide users through the Biomimicry Institute’s [Design Process](https://toolbox.biomimicry.org/methods/process/), a step-by-step method to propose biomimetic solutions to challenges. This process includes defining the problem, biologizing the challenge, discovering natural models, abstracting design strategies, and emulating nature's lessons.


BIDARA uses a simple one-page web interface to the OpenAI ChatGPT API. To use it, you need to register for [an OpenAI API key](https://platform.openai.com/account/api-keys) first. All messages are stored in your browser's local storage, so everything is **private**. You can also close the browser tab and come back later to continue the conversation.

## Features
* **Open source**: BIDARA is open source ([GPL-3.0](/LICENSE)), so you can host it yourself and make changes as you want.
* **Private**: All chats and messages are stored in your browser's local storage, so everything is private.
* **Customizable**: You can customize the prompt, the temperature, and other model settings. Multiple models (including GPT-4) are supported.
* **Cheaper**: BIDARA uses the commercial OpenAI API, so it's much cheaper than a ChatGPT Plus subscription.
* **Fast**: BIDARA is a single-page web app, so it's [fast and responsive](https://pagespeed.web.dev/analysis/https-niek-github-io-chatgpt-web/8xv5uwrnes).
* **Mobile-friendly**: BIDARA is mobile-friendly, so you can use it on your phone.
* **Voice input**: BIDARA supports voice input, so you can talk to BIDARA. It will also talk back to you.
* **Export**: BIDARA can export chats as a Markdown file, so you can share them with others.
* **Code**: BIDARA recognizes and highlights code blocks and allows you to copy them with one click.
* **Desktop app**: BIDARA can be bundled as a desktop app, so you can use it outside of the browser.
* **Image generation**: BIDARA can generate images using the DALL·E model by using the prompt "show me an image of ...".
* **Streaming**: BIDARA can stream the response from the API, so you can see the response as it's being generated.

## Development

To run the development server, run

```bash
npm ci
npm run dev # or: npm run build
```

To update the [`awesome-chatgpt-prompts`](/src/awesome-chatgpt-prompts/) subtree, run :
```bash
git subtree pull --prefix src/awesome-chatgpt-prompts https://github.com/f/awesome-chatgpt-prompts.git main --squash
```

## Use with Docker compose

```bash
docker compose up -d
```

## Mocked api
If you don't want to wait for the API to respond, you can use the mocked API instead. To use the mocked API, edit the `.env` file at root of the project and set the key `VITE_API_BASE=http://localhost:5174` in it. Then, run the `docker compose up -d` command above.

You can customize the mocked API response by sending a message that consists of `d` followed by a number, it will delay the response the the specified number of seconds. You can customize the length of the response by including `l` followed by a number, it will return a response with the specified number of sentences.
For example, sending the message `d2 l10` will result in a 2 seconds delay and 10 sentences response.

## Desktop app

You can also use BIDARA as a desktop app. To do so, [install Rust first](https://www.rust-lang.org/tools/install). Then, simply run `npm run tauri dev` for the development version or `npm run tauri build` for the production version of the desktop app. The desktop app will be built in the `src-tauri/target` folder.

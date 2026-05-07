# chatgpt-share-parser

Typescript ChatGPT shared conversation link parser.

[npm](https://www.npmjs.com/package/chatgpt-share-parser) · [GitHub](https://github.com/evanhu1/chatgpt-share-parser)

This is a small TypeScript module ported from [ChatPeek](https://github.com/vl3c/ChatPeek) for use in JavaScript and TypeScript projects.

## Install

```sh
pnpm add chatgpt-share-parser
```

## Usage

```ts
import {
  chatGptShareToMarkdown,
  fetchChatGptShare,
  parseChatGptShareHtml,
} from "chatgpt-share-parser";

const chat = await fetchChatGptShare(
  "https://chatgpt.com/share/your-public-share-id",
);

console.log(chat.title);
console.log(chat.replies.length);
console.log(chatGptShareToMarkdown(chat));
```

If you already have the HTML, parse it directly:

```ts
const chat = parseChatGptShareHtml(html);
```

## API

- `fetchChatGptShare(url)` fetches and parses a public ChatGPT share URL.
- `fetchChatGptShareHtml(url)` fetches the raw share HTML with browser-like headers.
- `parseChatGptShareHtml(html)` parses modern React Flight shares and falls back to legacy `__NEXT_DATA__` shares.
- `chatGptShareToMarkdown(chat)` renders a parsed conversation to Markdown.
- `getChatGptShareId(url)` extracts a share id from `chatgpt.com/share/...` or `chat.openai.com/share/...`.
- `isChatGptShareUrl(url)` returns whether a URL is a supported public share URL.

## Notes

This library is intended for personal exports of public ChatGPT shared conversations. It does not access private chats or authenticated APIs.

## License

MIT

# Markdown Area Element

**MarkDown Editor** element based on [Web Components][1] & [WebCell v2][2]

[![NPM Dependency](https://david-dm.org/EasyWebApp/markdown-area-element.svg)][3]
[![CI & CD](https://github.com/EasyWebApp/markdown-area-element/workflows/CI%20&%20CD/badge.svg)][4]

[![NPM](https://nodei.co/npm/markdown-area-element.png?downloads=true&downloadRank=true&stars=true)][5]

## Usage

```tsx
import { documentReady, render, createCell } from 'web-cell';
import { FileCellProps, FileCell } from 'file-cell';
import { MarkdownAreaElement } from 'markdown-area-element';

const upload: FileCellProps['transport'] = async file => {
    const response = await fetch('/file', {
        method: 'POST',
        body: file
    });
    const { path } = await response.json();

    return { path };
};

documentReady.then(() =>
    render(
        <FileCell transport={upload}>
            <MarkdownAreaElement name="markdown">
                default text
            </MarkdownAreaElement>
        </FileCell>
    )
);
```

[1]: https://www.webcomponents.org/
[2]: https://web-cell.dev/
[3]: https://david-dm.org/EasyWebApp/markdown-area-element
[4]: https://github.com/EasyWebApp/markdown-area-element/actions
[5]: https://nodei.co/npm/markdown-area-element/

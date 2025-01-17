# file-type-mime
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fredmundas%2Ffile-type-mime.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fredmundas%2Ffile-type-mime?ref=badge_shield)

Utility to parse mime type from a binary file

## Examples

**Browser (react)**

```javascript
import parse from 'file-type-mime';

export default function fileUpload() {
  async function onChange(e) {
    const [file] = e.target.files;
    const buffer = await file.arrayBuffer();
    const result = parse(buffer);

    console.log('MIME_TYPE', result);
  }

  return (
    <form>
      <input type="file" onChange={onChange}>
    </form>
  );
}
```

**Node.js**

```javascript
import parse from 'file-type-mime';
import { readFileSync } from 'node:fs';
import { resolve } from 'node:path';

const file = resolve('./path/to/file.pdf');
const buffer = readFileSync(file);
const result = parse(buffer);

console.log('MIME_TYPE', result);
```

## Supported file types

(more to come...)

| File extension | Content (mime) type |
| -------------- | ------------------- |
| bmp  | image/bmp |
| gif  | image/gif |
| ico  | image/x-icon |
| jpg  | image/jpeg |
| heic | image/heic |
| png  | image/png |
| tiff | image/tiff |
| pdf  | application/pdf |
| rtf  | application/rtf |
| epub | application/epub+zip |
| gz   | application/gzip |
| jar  | application/java-archive |
| zip  | application/zip |
| bz2  | application/x-bzip2 |
| rar  | application/x-rar-compressed |
| tar  | application/x-tar |
| docx | application/vnd.openxmlformats-officedocument.wordprocessingml.document |
| pptx | application/vnd.openxmlformats-officedocument.presentationml.presentation |
| xlsx | application/vnd.openxmlformats-officedocument.spreadsheetml.sheet |
| opd  | application/vnd.oasis.opendocument.presentation |
| ods  | application/vnd.oasis.opendocument.spreadsheet |
| odt  | application/vnd.oasis.opendocument.text |
| 7z   | application/x-7z-compressed |
| avi  | video/x-msvideo |
| mp3  | audio/mp3 |
| mp4  | video/mp4 |
| oga  | audio/ogg |
| ogg  | audio/ogg |
| ogm  | video/ogg |
| ogv  | video/ogg |
| ogx  | application/ogg |
| wav  | audio/wav |


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fredmundas%2Ffile-type-mime.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fredmundas%2Ffile-type-mime?ref=badge_large)
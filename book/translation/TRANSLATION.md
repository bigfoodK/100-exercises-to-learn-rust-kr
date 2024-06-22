# Translation

This document assumes that you are using [mdbook-i18n-helpers](https://github.com/google/mdbook-i18n-helpers/blob/main/i18n-helpers/USAGE.md).

## Installation

To install, run:

```shell
cargo install mdbook-i18n-helpers
```

## Preparing For Translation

### Create `messages.pot` File

Run the following command in the `book` directory (not the root of the repository):

```shell
MDBOOK_OUTPUT='{"xgettext": {}}' \
  mdbook build -d po
```

This will create `book/po/messages.pot`.

### Create New `xx.po` File

Run the following command in the `book` directory (not the root of the repository):

```shell
msginit -i po/messages.pot -l xx -o po/xx.po
```

This will create `book/po/xx.po`. Replace `xx` with your [language code](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes). You can now start the translation process.

## Using Translated Book

### Build

To build the translated book, run:

```shell
MDBOOK_BOOK__LANGUAGE=xx mdbook build -d book/xx
```

### Serve

To serve the translated book locally, run:

```shell
MDBOOK_BOOK__LANGUAGE=xx mdbook serve
```

## More Information

This is a simplified guide. For more details, refer to [i18n-helpers/USAGE.md](https://github.com/google/mdbook-i18n-helpers/blob/main/i18n-helpers/USAGE.md).

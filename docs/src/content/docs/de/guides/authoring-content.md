---
Titel: Inhalte in Markdown verfassen
Beschreibung: Ein Überblick über die von Starlight unterstützte Markdown-Syntax.
---

Starlight unterstützt die gesamte Bandbreite der [Markdown](https://daringfireball.net/projects/markdown/) Syntax in `.md`-Dateien sowie Frontmatter [YAML](https://dev.to/paulasantamaria/introduction-to-yaml-125f), um Metadaten, wie Titel und Beschreibung, zu definieren.

Bitte prüfe die [MDX docs](https://mdxjs.com/docs/what-is-mdx/#markdown) oder [Markdoc docs](https://markdoc.dev/docs/syntax), wenn Du diese Dateiformate verwendest, da die Unterstützung und Verwendung von Markdown unterschiedlich sein kann.

## Inline-Stile

Text kann **fett**, _italic_, oder ~~durchgestrichen~~ sein.

```md
Text kann **fett**, _italic_, oder ~~durchgestrichen~~ sein.
```

Du kannst [auf eine andere Seite](/getting-started/) verlinken.

```md
Du kannst [auf eine andere Seite](/getting-started/) verlinken.
```

Du kannst `inline code` mit Backticks hervorheben.

```md
Du kannst `inline code` mit Backticks hervorheben.
```

## Bilder

Bilder in Starlight verwenden [Astros eingebaute optimierte Asset-Unterstützung](https://docs.astro.build/en/guides/assets/).

Markdown und MDX unterstützen die Markdown-Syntax für die Anzeige von Bildern, die Alt-Texte für Screenreader und andere Tools zur Unterstützung enthält.

![Eine Illustration von Planeten und Sternen mit dem Wort "Astro"](https://raw.githubusercontent.com/withastro/docs/main/public/default-og-image.png)

```md
![Eine Illustration von Planeten und Sternen mit dem Wort "astro"](https://raw.githubusercontent.com/withastro/docs/main/public/default-og-image.png)
```

Relative Bildpfade werden auch für Bilder unterstützt, die lokal in Deinem Projekt gespeichert sind.

```md
// src/content/docs/page-1.md

![Ein Raketenschiff im Weltraum](../../assets/images/rocket.svg)
```

## Überschriften

Du kannst den Inhalt mit Überschriften strukturieren. Überschriften in Markdown werden durch eine Reihe von `#` am Anfang der Zeile gekennzeichnet.

### Wie Du Seiteninhalte in Starlight strukturierst

Starlight ist so konfiguriert, dass es automatisch den Seitentitel als Überschrift verwendet und eine "Übersicht"-Überschrift an den Anfang des Inhaltsverzeichnisses jeder Seite setzt. Wir empfehlen, jede Seite mit normalem Text zu beginnen und die Seitenüberschriften ab `<h2>` zu verwenden:

```md
---
Titel: Markdown Anleitung
description: Wie man Markdown in Starlight benutzt
---

Diese Seite beschreibt, wie man Markdown in Starlight benutzt.

## Inline-Stile

## Überschriften
```

### Automatische Überschriften-Ankerlinks

Wenn Du Überschriften in Markdown verwendest, erhalten Sie automatisch Ankerlinks, so dass Du direkt auf bestimmte Abschnitte der Seite verlinken kannst:

```md
---
Titel: Meine Seite mit Inhalt
Beschreibung: Wie man Starlight's eingebaute Ankerlinks benutzt
---

## Einleitung

Ich kann auf [meine Schlussfolgerung](#Schlussfolgerung) weiter unten auf derselben Seite verlinken.

## Schlussfolgerung

`https://my-site.com/page1/#introduction` navigiert direkt zu meiner Einleitung.
```

Überschriften der Ebene 2 (`<h2>`) und der Ebene 3 (`<h3>`) werden automatisch im Inhaltsverzeichnis der Seite angezeigt.

## Nebenbemerkungen

Nebenbemerkungen (auch bekannt als "Asides" oder "Callouts") sind nützlich, um sekundäre Informationen neben dem Hauptinhalt einer Seite anzuzeigen.

Starlight bietet eine eigene Markdown-Syntax für die Darstellung von Nebeninformationen. Sie werden mit dreifachen Doppelpunkten `:::` um den Inhalt angezeigt und können vom Typ `note`, `tip`, `caution` oder `danger` sein.

Es können alle anderen Markdown-Inhaltstypen innerhalb einer aside verschachtelt werden, allerdings eignen sie sich am besten für kurze und prägnante Aussagen.

### Note Bemerkung

:::note
Starlight ist ein Toolkit für Dokumentations-Websites, das mit [Astro](https://astro.build/) erstellt wurde. Du kannst mit diesem Befehl beginnen:

```sh
npm create astro@latest -- --template starlight
```

:::

````md
:::note
Starlight ist ein Toolkit für Dokumentations-Websites, das mit [Astro](https://astro.build/) erstellt wurde. Du kannst mit diesem Befehl beginnen:

```sh
npm create astro@latest -- --template starlight
```

:::
````

### Benutzerdefinierte Seitentitel

Du kannst einen benutzerdefinierten Titel für die Bemerkung in eckigen Klammern nach dem Typ angeben, z.B. `:::tip[Wussten Sie schon?]`.

:::tip[Wussten Sie schon?]
Astro hilft Ihnen, schnellere Websites mit ["Islands Architecture"](https://docs.astro.build/en/concepts/islands/) zu erstellen.
:::

```md
:::tip[Wussten Sie schon?]
Astro hilft Ihnen, mit der ["Islands Architecture"](https://docs.astro.build/en/concepts/islands/) schnellere Websites zu erstellen.
:::
```

### Mehr Bemerkungs-Typen

`caution` und `danger` Bemerkungen are helpful for drawing a user’s attention to details that may trip them up.
If you find yourself using these a lot, it may also be a sign that the thing you are documenting could benefit from being redesigned.

:::caution
If you are not sure you want an awesome docs site, think twice before using [Starlight](../../).
:::

:::Gefahr
Ihre Benutzer können dank hilfreicher Starlight-Funktionen produktiver sein und Ihr Produkt einfacher nutzen.

- Übersichtliche Navigation
- Benutzer-konfigurierbares Farbthema
- [i18n-Unterstützung](/guides/i18n)

:::

```md
:::Vorsicht
Wenn Sie sich nicht sicher sind, ob Sie eine tolle Dokumentseite wollen, denken Sie zweimal nach, bevor Sie [Starlight](../../) verwenden.
:::

:::danger
Your users may be more productive and find your product easier to use thanks to helpful Starlight features.

- Übersichtliche Navigation
- Benutzer-konfigurierbares Farbthema
- [i18n-Unterstützung](/guides/i18n)

:::
```

## Blockquotes

> This is a blockquote, which is commonly used when quoting another person or document.
>
> Blockquotes are indicated by a `>` at the start of each line.

```md
> This is a blockquote, which is commonly used when quoting another person or document.
>
> Blockquotes are indicated by a `>` at the start of each line.
```

## Code blocks

A code block is indicated by a block with three backticks <code>```</code> at the start and end. You can indicate the programming language being used after the opening backticks.

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l);
  return true;
};
```

````md
```js
// Javascript-Code mit Syntaxhervorhebung.
var fun = Funktion lang(l) {
  dateformat.i18n = require('./lang/' + l);
  return true;
};
```
````

````md
Lange, einzeilige Codeblöcke sollten nicht umgebrochen werden. Sie sollten horizontal scrollen, wenn sie zu lang sind. Diese Zeile sollte lang genug sein, um dies zu demonstrieren.
```

## Andere allgemeine Markdown-Funktionen

Starlight unterstützt alle anderen Markdown-Autorensyntaxen, wie Listen und Tabellen. Einen schnellen Überblick über alle Markdown-Syntaxelemente finden Sie im [Markdown Cheat Sheet from The Markdown Guide](https://www.markdownguide.org/cheat-sheet/).

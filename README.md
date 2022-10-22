# Text Highlighter Tool

A flutter package to highlight words and word parts from a text.

Fork of [highlight_text](https://github.com/desconexo/highlight_text) by [desconexo](https://github.com/desconexo).
Differences from the original:
* Simplification: words in `HighlightedWord` class now can not be highlighted with `decoration` and `padding` properties to avoid known issues with text vertical alignment.


## Usage

To use this package, add `text_highlighter` as a [dependency in your pubspec.yaml file](https://flutter.io/platform-plugins/).

## Getting Started

With this package you can highlight words and create specific actions for each highlighted word, you can customize the style of each word separately or create a unique style for all of them, you can also customize the style of the rest of the text.

## Example

Import the highlight library
``` dart
import 'package:text_highlighter/text_highlighter.dart';
```

You should use the `HighlightedWord` class to specify the dictionary words in a Map object
``` dart
Map<String, HighlightedWord> words = {
    "Flutter": HighlightedWord(
        onTap: () {
            print("Flutter");
        },
        textStyle: textStyle,
    ),
    "open-source": HighlightedWord(
        onTap: () {
            print("open-source");
        },
        textStyle: textStyle,
    ),
    "Android": HighlightedWord(
        onTap: () {
            print("Android");
        },
        textStyle: textStyle,
    ),
};
```

Now you can call the `TextHighlight` widget
``` dart
TextHighlight(
    text: text, // You need to pass the string you want the highlights
    words: words, // Your dictionary words
    textStyle: TextStyle( // You can set the general style, like a Text()
        fontSize: 20.0,
        color: Colors.black,
    ),
    textAlign: TextAlign.justify, // You can use any attribute of the RichText widget
),
```
# Social Embed WebView (Developers Preview) 
Currentlty non of the major social media platform provide support to embed their post in flutter app. This flutter package provides widget to embed post of various social media platform using [webview_flutter](https://pub.dev/packages/webview_flutter) in background.

## Content
* [Social Embed WebView](#social-embed-webView)
* [Why Us](#why-us)
* [Supported Platforms](#supported-platforms)
* [How to use?](#how-to-use)
* [Examples](#example)

## Why Us
They are not many solution in the community to slove this problem. All the  packages uses same [webview_flutter](https://pub.dev/packages/webview_flutter) in background but have a major issue of a *predefined height*. While this package *adjusts the heights of the webview automatically* accoording to the size of embedded post.

## Supported Platforms:
* [Instagram](https://instagram.com/)
* [Twitter](https://twitter.com)
* [Youtube](https://youtube.com/)

`Facebook Support Comming Soon!!!`

## How to use?
**1:** Add this to your package's pubspec.yaml file:

```yaml
dependencies:
  social_embed_webview: ^0.2.1+9
```

**2:** You can install packages from the command line:

```bash
$ flutter packages get
```

Alternatively, your editor might support flutter packages get. Check the docs for your editor to learn more.


**3:** Please visit [webview_flutter](https://pub.dev/packages/webview_flutter_plus#how-to-use) and steps required for implementations in `Android` and `iOS` respectively

## Example
Please make sure to remove `<script>...</script>` added by the platform with other embed code.

```
import 'package:flutter/material.dart';
import 'package:social_embed_webview/social_embed_webview.dart';

String tweetContent = r"""
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Here’s an edit I did of one of my drawings. I tend to draw a lot of aot stuff when each chapter is released. Sorry about that!<br>Song: polnalyubvi кометы<br>Character: Annie Leonhart <a href="https://twitter.com/hashtag/annieleonhart?src=hash&amp;ref_src=twsrc%5Etfw">#annieleonhart</a> <a href="https://twitter.com/hashtag/aot131spoilers?src=hash&amp;ref_src=twsrc%5Etfw">#aot131spoilers</a> <a href="https://twitter.com/hashtag/aot?src=hash&amp;ref_src=twsrc%5Etfw">#aot</a> <a href="https://twitter.com/hashtag/AttackOnTitan131?src=hash&amp;ref_src=twsrc%5Etfw">#AttackOnTitan131</a> <a href="https://twitter.com/hashtag/AttackOnTitans?src=hash&amp;ref_src=twsrc%5Etfw">#AttackOnTitans</a> <a href="https://twitter.com/hashtag/snk?src=hash&amp;ref_src=twsrc%5Etfw">#snk</a> <a href="https://twitter.com/hashtag/snk131?src=hash&amp;ref_src=twsrc%5Etfw">#snk131</a> <a href="https://twitter.com/hashtag/shingekinokyojin?src=hash&amp;ref_src=twsrc%5Etfw">#shingekinokyojin</a> <a href="https://t.co/b4z48ruCoD">pic.twitter.com/b4z48ruCoD</a></p>&mdash; evie (@hazbin_freak22) <a href="https://twitter.com/hazbin_freak22/status/1291884358870142976?ref_src=twsrc%5Etfw">August 7, 2020</a></blockquote> """;

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: SafeArea(
        child: Scaffold(
          appBar: AppBar(
            title: Text('Social Embed WebView Example'),
          ),
          body: SingleChildScrollView(
            child: Padding(
              padding: const EdgeInsets.all(8.0),
              child: Column(
                children: [
                  SocialEmbed(
                    embedCode: tweetContent,
                    type: SocailMediaPlatforms.twitter,
                  )
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}

```
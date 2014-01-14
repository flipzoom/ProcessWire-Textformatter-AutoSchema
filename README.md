#ProcessWire – AutoSchema Textformatter#

####Automatic Schema.org Micro Data for basic elements####
-----------------------------

AutoSchema module automatically sets the basic micro data attributes of Schema.org. For example, for headings, paragraphs, images and links. Images are automatically changed to a HTML5 figure tag and the image alt attribut used as caption. This option can be disabled via the backend.

##Installation##

1. Copy the files for this module to /site/modules/TextformatterAutoSchema/
2. In admin: Modules > Check for new modules. Install Module > AutoSchema - Auto detect of Schema.org-Attributes
3. Add AutoSchema as Textformatter on a Textfield. The best way as last formatter.

##Example what happens##

In the "body"-field (for example, editable via the CKEditor) you add an image. When you render the template following tag is displayed without AutoSchema:

```html
<img alt="Your image caption" width="600" height="400" src="/site/assets/files/1/my-image.600x0.jpg" />
```

AutoSchema automatically generates the following code:

```html
<figure itemscope itemtype="http://schema.org/ImageObject" style="width:600px;">
    <img alt="Your image caption" width="600" height="400" src="/site/assets/files/1/my-image.600x0.jpg"  itemprop="image" />
    <figcaption itemprop="caption">Your image caption</figcaption>
    <meta itemprop="width" content="600">
    <meta itemprop="height" content="400">
</figure>
```

##What is changed automatically?##

* ```<h1>``` to ```<h1 itemprop="headline">```
* ```<h2-6>``` to ```<h2-6 itemprop="alternativeHeadline">```
* ```<p>``` to ```<p itemprop="text">```
* ```<a>``` to ```<a itemprop="url">```
* ```<img>``` to ```<img itemprop="image" />``` or complete HTML5 figure

##What are micro data and this Schema.org?##

Schema.org provides a collection of shared vocabularies webmasters can use to mark up their pages in ways that can be understood by the major search engines: Google, Microsoft, Yandex and Yahoo! More information: [schema.org](http://schema.org/)

##Changelog##

1.0.0  
* Initial release

##Questions or comments?##

My Name is David Karich. Send me an E-Mail with your questions, suggestions or bugs to support@flipzoom.de. 

##Test environment##

* ProcessWire in Version 2.3
* Windows (WAMP) / Linux (CentOS 6.4/6.5)
* PHP 5.3.3, 5.5.3
* Apache 2.2.21

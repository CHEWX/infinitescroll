# jquery infinitescroll

A demo page is currently [here](http://infinitescroll.zedler.it/demo/page1.html)



## Usage

```
<script src="<some_path>/jquery.min.js"></script>
<script src="<some_path>/jquery.infinitescroll.js"></script>
<script>
    $('.row').infinitescroll({
        itemSelector: '.col',
        nextSelector: '.next-page',
        bufferPx: 40,
        callback: function() {
            console.log('Page Loaded');
        },
    });
</script>
```

An Ajax call takes place when the first element matching the
`nextSelector` comes closer to the window bottom than the pixels
defined in `bufferPx` during scrolling.

The Ajax call fetches that page which is defined in the `href` of the
first link matching `nextSelector`.

The elements of the fetched page matching `itemSelector` are appended
to the jQuery collection.

Add anonymous function to the callback option which is called after the
items are added to the DOM.

If the next page has an element matching `nextSelector` as well,
the whole procedure repeats.

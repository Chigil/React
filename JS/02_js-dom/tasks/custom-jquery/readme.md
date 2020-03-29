# Custom jQuery

## Short Description

Implement minimal version of jQuery using DOM API Methods.

## Estimation (h)

40

## Topics

1. Document
2. Browser Events

## Requirements

* Implement the following methods from the [jQuery](https://jquery.com/) library:

-   [addClass](http://api.jquery.com/addClass/)
-   [removeClass](http://api.jquery.com/removeClass/)
-   [append](http://api.jquery.com/append/)
-   [remove](http://api.jquery.com/remove/)
-   [text](http://api.jquery.com/text/)
-   [attr](http://api.jquery.com/attr/)
-   [children](http://api.jquery.com/children/)
-   [empty](http://api.jquery.com/empty/)
-   [css](http://api.jquery.com/css/)
-   [click](http://api.jquery.com/click/)

## Advanced Requirements

1. Add more methods:

-   [each](http://api.jquery.com/each/)
-   [toggle](http://api.jquery.com/toggle/)
-   [wrap](http://api.jquery.com/wrap/)

2. Implement chaining functionality as at the following example:

```javascript
$('.my-class')
    .each(function (index) {
        $(this).html('<b>' + index + '</b>')
    })
    .append($('div'))
    .addClass('my-super-class')
    .css({
        backgroundColor: 'rebeccapurple'
    });
```

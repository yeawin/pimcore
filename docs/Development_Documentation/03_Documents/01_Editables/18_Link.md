# Link

## General 

The link editable is used for dynamic link creation based on documents, 
assets and for structured links, which shouldn't be inside WYSIWYG (for example external link).

## Configuration

You can pass every valid attribute an a-tag can have ([w3.org - Link](http://www.w3.org/TR/html401/struct/links.html#h-12.2)), such as:

* class
* target
* id
* style
* accesskey
* name
* title

| Name   | Type     | Description                                                             |
|--------|----------|-------------------------------------------------------------------------|
| reload | boolean  | Set to true to reload the page in editmode after changing the state.    |

## Methods

| Name            | Return-Type | Description                      |
|-----------------|-------------|----------------------------------|
| getHref()       | string      | get the path of this link        |
| getText()       | string      | get the text of the link         |
| getTarget()     | string      | get the target of the link       |
| getParameters() | string      | get the query params of the link |
| getAnchor()     | string      | get the anchor text of the link  |
| getTitle()      | string      | get the title of the link        |
| getRel()        | string      | get the rel text of the link     |
| getTabindex()   | string      | get the tabindex of the link     |
| getAccessKey()  | string      | get the access key of the link   |
| isEmpty()       | string      | empty or not                     |

## Examples

### Basic usage

In this example I created the link with some static page to the internal blog page.

```php
<p>
    Visit our <?php echo $this->link("blogLink"); ?>
</p>
```

You could see the backend preview in the picture, below.

![Link editable - adminitration panel](../../img/editables_link_backend_preview.png)

And the frontend:

![Link editable - frontend](../../img/editables_link_frontend_preview.png)



### Use link in the block editable

Let's see how to make a list of links with [Block](./06_Block.md).

```php
<p>Useful links:</p>
<ul>
    <?php while ($this->block("linkblock")->loop()): ?>
        <li>
            <?php echo $this->link("myLink", ["class" => "special-link-class"]); ?>
        </li>
    <?php endwhile; ?>
</ul>
```

The above example renders the block list, there is possible to add unlimited rows with Link editable.

![The links list in the backend](../../img/editables_link_inside_block.png)






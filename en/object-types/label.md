# Label (lv_label)

## Overview
The Labels are the basic objects to **display text**. There is no limitation in the text size because it's stored dynamically. You can modify the text in runtime at any time with `lv_label_set_text(label, "New text")`.

You can use `\n` to make line break. For example: `"line1\nline2\n\nline4"`

The size of the label object can be automatically expanded to the text size or the text can be manipulated according to several **long mode policies**:
* **LV_LABEL_LONG_EXPAND** Expand the object size to the text size (Default)
* **LV_LABEL_LONG_BREAK** Keep the object width, break (wrap) the too long lines and expand the object height
* **LV_LABEL_LONG_DOTS** Keep the object size, break the text and write dots in the last line
* **LV_LABEL_LONG_ROLL** Keep the size and scroll the label back and forth
* **LV_LABEL_LONG_ROLL_CIRC** Keep the size and scroll the label circurally
* **LV_LABEL_LONG_CROP** Keep the size and crop the text out of it.

You can specify the long mode with: `lv_label_set_long_mode(label, LV_LABEL_LONG_...)`

It's important to note that when a label is created and its test is set the label's size alraedy expanded to the text size. 
In addition with the default `LV_LABEL_LONG_EXPAND` *long mode* `lv_obj_set_width/height/size()` has no effect.
So you need to change the *long mode* first and then set the size with  `lv_obj_set_width/height/size()` .

Labels are able to show text from a **static array**. Use: `lv_label_set_static_text(label, char_array)`. 
In this case, the text is not stored in the dynamic memory but the given array is used directly instead. 
Keep in my the array can't be a local variable which destroys when the function exits.

You can also use a **raw character array** as label text. 
The array doesn't have to be `\0` terminated. In this case, the text will be saved to the dynamic memory. 
To set a raw character array use the `lv_label_set_array_text(label, char_array)` function.

The label's **text can be aligned** to the left, right or middle with `lv_label_set_align(label, LV_LABEL_ALIGN_LEFT/RIGHT/CENTER)`

You can enable to **draw a background** for the label with `lv_label_set_body_draw(label, draw)`

In the text, you can use commands to **re-color parts of the text**. For example: `"Write a #ff0000 red# word"`. 
This feature can be enabled individually for each label by `lv_label_set_recolor()` function. 

The labels can display symbols besides letters. Read the [Font](/overview/fonts) section to lear more about the symbols.

The labels' **default style** is `NULL` so they inherit the parent's style.

## Styles
The Label uses one style which can be set by `lv_label_set_style(label, LV_LABEL_STYLE_MAIN, &style)`. Form the style the following properties are used:
* all properties from `style.text`
* for background drawing `style.body` properties. `padding` will increase the size only visually, the real object size on't be changed.

## Events
Only the [Genreric events](/overview/events.html#generic-events) are sent by the object type.

Learn more about [Events](/overview/events).

## Keys
No *Keys* are not processed by the object type.

Learn more about [Keys](/overview/indev).



## Example

### C


![](/examples/label/label_1.png "Label example in LittlevGL")

```eval_rst
.. container:: toggle

    .. container:: header
    
      code

    .. literalinclude:: /examples/label/label_1.c
      :language: c
 
```

### MicroPython
No examples yet.

## API 

```eval_rst

.. doxygenfile:: lv_label.h
  :project: lvgl
        
```


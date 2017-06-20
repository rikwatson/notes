# Converting XML to JSON

C# and `.net` are a very XML oriented technology suite (Hello `.net`), however HTML5 apps aren't.
Unfortunatly there is no direct translation which can be successfully applied between the two formats. [JSON](./json.md) lacks attributes (`a=b`) and multiple objects (See `<Item>` in the example below).

Even if we consider the subset of XML used within our add (No....) then life is still non-trivial.

Attribute representing in JSON

```xml
<XML a=b>
    <Item>
        Text
    <\Item>
    <Item>
        Text
    <\Item>
<\XML>
```

Becomes

```json
{
    "_" : 
        {
            A: B
        },

    Item: {
        Text: null
        }
}
```
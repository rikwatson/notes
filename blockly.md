# Blockly

Blockly is a graphical "block" based UI primarilarly designed as a programming teaching aid. However, because the blocks are easily extendable, Blockly can be used for many
differing projects.

[Blockly](https://developers.google.com/blockly/guides/get-started/web) is a Google visual programming environment which is easily configurable to provide a drag-and-drop toolbox suitable for various tasks within many applications.

Blockly is written in HTML5 and can be embedded into apps or (static) sites with easy.

It is extensible in a way that allows extra 'blocks' (wiith their own semantics) and code generation to be added. (& unnecessary blocks to be hidden.)

 * [Getting Started guide](https://developers.google.com/blockly/guides/get-started/web)

 * [Documentation](blockly.xml-structure.md) on the `XML` side of Blockly's structure (.v. the [JSON](./json.md) which is used to define blocks)

## Links

 * Introduction to [Blockly](https://developers.google.com/blockly/guides/overview)
 * [Creating](https://developers.google.com/blockly/guides/create-custom-blocks/overview) custom blocks
 * Blockly Developer Tools
   * [Docs](https://developers.google.com/blockly/guides/create-custom-blocks/blockly-developer-tools)
   * [Site](https://blockly-demo.appspot.com/static/demos/blockfactory/index.html), use blockly to create blocks
   * Usage [video](https://www.youtube.com/watch?v=s2_xaEvcVI0)

Blockly API [Workshop](blockly.api-workshop.pptx) (The Noughts & Crosses Example)

## The Toolbox

 * [Configuring](https://developers.google.com/blockly/guides/configure/web/toolbox)

 ```xml
 <xml id="toolbox" style="display: none">
  <category name="Control">
    <block type="controls_if"></block>
    <block type="controls_whileUntil"></block>
    <block type="controls_for">
  </category>
  <category name="Logic">
    <block type="logic_compare"></block>
    <block type="logic_operation"></block>
    <block type="logic_boolean"></block>
  </category>
</xml>
 ```

 [Dynamic](https://developers.google.com/blockly/guides/configure/web/toolbox#dynamic_categories) toolbox entrcategoriesies are also supported (Which are calculated everytime the specified category is opened)


## Notes for developers

1. Use the online [Blockly Developer Tools](https://blockly-demo.appspot.com/static/demos/blockfactory/index.html) provided by Google to create blocks. It's good for all but the most complicated of blocks and is significantly faster to use
than hand coding. Also save as JavaScript, not JSON as you can the perform JS injection etc (if necessary). 

2. When using the designed make a note of the URL given in the 'link' icon ![](./blockly.link.jpg) - store this with the code as it is then possible to go back to the online design to tweak the code.

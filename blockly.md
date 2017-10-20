# Blockly

Blockly is a graphical "block" based UI primarilarly designed as a programming teaching aid. However, because the blocks are easily extendable, Blockly can be used for many
differing projects.

## Links

 * Introduction to [Blockly](https://developers.google.com/blockly/guides/overview)
 * [Creating](https://developers.google.com/blockly/guides/create-custom-blocks/overview) custom blocks
 * Blockly Developer Tools
   * [Docs](https://developers.google.com/blockly/guides/create-custom-blocks/blockly-developer-tools)}
   * [Site](https://blockly-demo.appspot.com/static/demos/blockfactory/index.html), use blockly to create blocks
   * Usage [video](https://www.youtube.com/watch?v=s2_xaEvcVI0)

Blockly 'programs' are represented by a [xml structure](./blockly.xml-structure.2015.pdf) (NOTE: missing at least shadow blocks and variables)

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
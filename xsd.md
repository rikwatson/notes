# XSD

[XML](./xml.md), defined in XML.

## XSD Generation

  * [XSD/XML Schema Generator](http://www.freeformatter.com/xsd-generator.html#ad-output)

## How to write a XSD

Although I've created XSD's from grammers for most basic XML schema's it's actually easier to create an XSD manually from scratch!

Start with an XSD which will allow any (valid) XML for a specified root (`<root\>`) - **XML Schema can't specify that a document is valid regardless of its content**

```xml
<xs:element name="parameter" maxOccurs="unbounded" minOccurs="0">
<xs:complexType>
    <xs:sequence>
        <xs:any processContents="skip" minOccurs="0"/>
    </xs:sequence>
    <xs:attribute type="xs:string" name="name" use="optional"/>
    <xs:attribute type="xs:string" name="value" use="optional"/>
</xs:complexType>
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="root"/>
</xs:schema>
```

Which can be expanded into:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="root">
    <xs:complexType>
      <xs:sequence>
        <xs:any processContents="skip" minOccurs="0" maxOccurs="unbounded"/>
      </xs:sequence>
      <xs:anyAttribute processContents="skip"/>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

## Script to validate XML agaist an XSD

```bash
#!/bin/bash
#
# `xmllint --noout --schema XSD_FILE XML_FILE`
#
xmllint --noout --schema Config.xsd ./test_xml/a.XML
xmllint --noout --schema Config.xsd ./test_xml/b.XML

echo "Find..."


find ./test_xml -name "*.xml" -exec xmllint --noout --schema Config.xsd {} \;
```

----


## Links

 * [How to derive DTD (or other XML spec format) from XML file samples](http://stackoverflow.com/questions/1815216)
 * [Create an XML Schema from an XML Document](https://msdn.microsoft.com/en-us/library/ms255829.aspx)
 * Best Practices, [Global versus Local](http://www.xfront.com/GlobalVersusLocal.html)
 * [XML DOM Nodes](https://www.w3schools.com/xml/dom_nodes.asp)
 * [XML Schema (XSD) validation tool? [closed]](http://stackoverflow.com/questions/124865)
 * [W3C XML Schema (XSD) Validation online](http://www.utilities-online.info/xsdvalidation/#.WN6_kxLyuJV)
 * [XML Schema element Element](https://www.w3schools.com/xml/el_element.asp)

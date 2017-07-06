[Go to primary content](#BEGIN)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Java Platform, Enterprise Edition The Java EE Tutorial</strong><br />
<strong>Release 7 Java Platform, Enterprise Edition</strong><br />
E39031-02</td>
<td><table>
<tbody>
<tr class="odd">
<td> </td>
<td><a href="toc.htm"><img src="../../dcommon/gifs/toc.gif" alt="Go To Table Of Contents" /><br />
<span class="icon">Contents</span></a></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

-----

<table>
<tbody>
<tr class="odd">
<td><a href="jsf-configure007.htm"><img src="../../dcommon/gifs/leftnav.gif" alt="Previous" /><br />
<span class="icon">Previous</span></a> </td>
<td><a href="jsf-configure009.htm"><img src="../../dcommon/gifs/rightnav.gif" alt="Next" /><br />
<span class="icon">Next</span></a></td>
<td> </td>
</tr>
</tbody>
</table>

Beta Draft: 2017-06-12

# 16.8 Registering a Custom Validator

If the application developer provides an implementation of the
`javax.faces.validator.Validator` interface to perform validation, you
must register this custom validator either by using the
`@FacesValidator` annotation, as described in [Implementing the
Validator Interface](jsf-custom012.htm#BNAUX), or by using the
`validator` XML element in the application configuration resource file:

``` oac_no_warn
<validator>
    ...
    <validator-id>FormatValidator</validator-id>
    <validator-class>
        myapplication.validators.FormatValidator
    </validator-class>
    <attribute>
        ...
        <attribute-name>formatPatterns</attribute-name>
        <attribute-class>java.lang.String</attribute-class>
    </attribute>
</validator>
```

Attributes specified in a `validator` tag override any settings in the
`@FacesValidator` annotation.

The `validator-id` and `validator-class` elements are required
subelements. The `validator-id` element represents the identifier under
which the `Validator` class should be registered. This ID is used by the
tag class corresponding to the custom `validator` tag.

The `validator-class` element represents the fully qualified class name
of the `Validator` class.

The `attribute` element identifies an attribute associated with the
`Validator` implementation. It has required `attribute-name` and
`attribute-class` subelements. The `attribute-name` element refers to
the name of the attribute as it appears in the `validator` tag. The
`attribute-class` element identifies the Java type of the value
associated with the attribute.

[Creating and Using a Custom Validator](jsf-custom012.htm#BNAUW)
explains how to implement the `Validator` interface.

[Using a Custom Validator](jsf-custom012.htm#BNATV) explains how to
reference the validator from the page.

-----

<table style="width:66%;">
<colgroup>
<col width="33%" />
<col width="0%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><table style="width:96%;">
<colgroup>
<col width="0%" />
<col width="48%" />
<col width="48%" />
</colgroup>
<tbody>
<tr class="odd">
<td> </td>
<td><a href="jsf-configure007.htm"><img src="../../dcommon/gifs/leftnav.gif" alt="Previous" /><br />
<span class="icon">Previous</span></a> </td>
<td><a href="jsf-configure009.htm"><img src="../../dcommon/gifs/rightnav.gif" alt="Next" /><br />
<span class="icon">Next</span></a></td>
</tr>
</tbody>
</table></td>
<td><img src="../../dcommon/gifs/oracle.gif" alt="Oracle Logo" class="copyrightlogo" /> <a href="../../dcommon/html/cpyr.htm"><br />
<span class="copyrightlogo">Copyright © 2014, Oracle and/or its affiliates. All rights reserved.</span></a></td>
<td><table>
<tbody>
<tr class="odd">
<td> </td>
<td><a href="toc.htm"><img src="../../dcommon/gifs/toc.gif" alt="Go To Table Of Contents" /><br />
<span class="icon">Contents</span></a></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

ORACLE CONFIDENTIAL. For authorized use only. Do not distribute to third parties.

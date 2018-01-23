.. include:: /_static/inc_styles.txt

.. index:: usx; attributes
.. _usx_AttributeIndex:

Attributes
==========

.. contents::
	:depth: 2

-----

Attributes are a standard aspect of XML syntax and can be applied to any element. An element can have multiple unique attributes. Attributes define additional properties of elements. They are a means of extending the meta information contained within in a USX text.

Attributes are listed as pairs of **name** and corresponding **value** using the syntax: ``attribute="value"``. The attribute name is a single ASCII string. The value is wrapped in quotes.

.. code-block:: xml

	<char style="w" lemma="grace">

Nearly all USX elements contain a required **@style** attribute. For :ref:`<para> <usx-element_para>` and :ref:`<char> <usx-element_char>` elements, the @style attribute defines the type of :doc:`paragraph <parastyles>` or :doc:`character <charstyles>` element being marked. The @style attribute in USX is also (intentionally) closely associated to `USFM <http://ubsicap.github.io/usfm/index.html>`_ paragraph and character markers with the same definition.

Word Level Descriptive Attributes
---------------------------------

USX will formally provide additional descriptive attributes for a subset of :doc:`<char> @style types`. Each <char> element in this set will have a defined list of additional attribute(s), which are relevant to the overall purpose of the element.

Default Attribute
-----------------

The concept of a "default attribute" is only valid in USFM text. It was designed to reduce the amoung of metadata visible in the text when working with USFM. In the case of the `USFM specification <http://ubsicap.github.io/usfm/attributes/index.html>`_, a single default attribute may be defined for a given character marker, and does not require the attribute name to be written within the text. To be valid, the XML expression in USX must *always* contain the attribute name and its value.

In the preceding example, ``<char @style="w">`` accepts an additional attribute ``lemma``, which is the `default attribute <http://ubsicap.github.io/usfm/characters/index.html#usfmc-w-attr>`_ found in the USFM expression for the same text.

User Defined Attributes
-----------------------

Attributes may be added to <char> elements within a text beyond the defined set for the latest USX version (3.0 or later). These will not be considered strictly USX compliant, and there is no assurance that they will be supported by compliant software tools or processes. Future versions of USX may formally define additional attributes.

Any user defined attributes must begin with the prefix ``x-``.

.. code-block:: xml

	<char style="w" x-myattr="metadata">gracious</char>
	<char style="w" lemma="grace" x-myattr="metadata">gracious</char>

User defined attributes can be added to any USX :ref:`<char> <usx-element_char>` element, even if it is not within the list of @style tagged <char> elements officially providing descriptive attributes.

<char> @style Types Providing Additional Attributes
---------------------------------------------------

* :ref:`<char @style="w"> <usx-charstyle_w-attr>` (lemma, strong)
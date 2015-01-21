OpenAIRE Guidelines for Data Archives
=====================================

Introduction
------------

Aim
^^^
OpenAIRE gathers together research output related to European funding streams, with the aim of supporting open science and tracking research impact. This content consists of open access publications and related contextual information such as datasets, supplementary material, and research/project information.

Two other sets of OpenAIRE guidelines exist for repository managers:

- OpenAIRE Guidelines for Literature Repositories 3.0
- OpenAIRE Guidelines for CRIS systems (CERIF standard) – In draft

The OpenAIRE Guidelines for Data Archive Managers 2.0 will provide instruction for data archive managers to expose their metadata in a way that is compatible with the OpenAIRE infrastructure. The metadata from data archives should be included in the OpenAIRE information space, and exposed when data are related to an open access publication e.g. a dataset cited by an article. To access a pdf version the guidelines see here: http://dx.doi.org/10.5281/zenodo.6918

By implementing the OpenAIRE Guidelines, data archive managers are facilitating the creation of enhanced publications and building the stepping-stones for a linked data infrastructure for research.

Exposure and visibility of content from a range of European repositories will be significantly increased when a common and interoperable approach is taken as well as adhering to existing guidelines. OpenAIRE is happy to assist in adherence to these guidelines. This compatibility will lead to future interoperability between research infrastructures, and structured metadata is of benefit to individual data repositories and the scholarly community at large.

DataCite
^^^^^^^^
OpenAIRE has adopted the DataCite Metadata Schema as the basis for harvesting and importing metadata about datasets from data archives.

The core mission of DataCite is to build and maintain a sustainable framework that makes it possible to cite data through the use of persistent identifiers, DOIs.

OpenAIRE shares the goal of the DataCite Metadata Schema - to provide a domain agnostic metadata schema and provide interoperability through a small number of properties - making interoperability possible in the simplest manner possible and as a result keep the technical barriers for implementation as low as possible.

We would like to thank DataCite for their kind support and help making these OpenAIRE Guidelines for Data Archive Managers possible.

What's different
^^^^^^^^^^^^^^^^
In this document you will find the needed properties to make your data archive compatible with the OpenAIRE infrastructure. OpenAIRE has adopted the DataCite Metadata Schema version 3.0 with some minor adjustments.

- OpenAIRE accepts other persistent identifier schemes and not only a DOI in 1.1 identifierType.
- OpenAIRE recommends exporting links to related publications and datasets (i.e. 12. RelatedIdentifier property and attributes are mandatory when applicable).
- OpenAIRE recommends using the 7. Contributor property to relate a dataset to funding information.
- DataCite optional properties 8. Date and 17. Description are mandatory in OpenAIRE.
- OpenAIRE enforces an encoding scheme on DataCite property 16. Rights.

Acknowledgements & Contributors
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**Editors**

- Mikael K. Elbæk (Technical University of Denmark)
- Lars Holm Nielsen (CERN, Switzerland)

**Experts & Reviewers**

- Samuele Kaplun (CERN, Switzerland)
- Paolo Manghi (CNR, Italy)
- Natalia Manola (University of Athens, Greece)
- Jochen Schirrwagen (University of Bielefeld, Germany)
- Birgit Schmidt (University of Goettingen,Germany)
- Mathias Lösch (University of Bielefeld, Germany)
- Frauke Ziedorn (DataCite, Germany)
- Pedro Principe (University of Minho, Portugal)
- Eloy Rodrigues (University of Minho, Portugal)
- Najla Rettberg (University of Goettingen, Germany)

OpenAIRE application of DataCite Metadata Schema
------------------------------------------------
OpenAIRE builds on the DataCite Metadata Schema v3.0 by making some of the otherwise optional DataCite properties mandatory, as well as enforcing specific encoding schemes on the values of some DataCite properties. The table below details the differences from the DataCite Metadata Schema.

Within OpenAIRE the use of properties are either:

- mandatory (M) = the property must always be present in the metadata record. An empty property is not allowed.
- mandatory when applicable (MA) = when the property can be obtained it must be present in the metadata record
- recommended (R) = the use of the property is recommended
- optional (O) = the property may be used to provide complementary information about the resource

The recommended status is made primarily to encourage users to input certain properties when creating a metadata record to enhance services.

.. important::

   The table below details only differences from the DataCite Metadata Schema v3.0. Please refer to the DataCite Metadata Schema v3.0 for definition of properties and their encoding schemes: http://schema.datacite.org/meta/kernel-3/index.html

===== ===================== ====== =================================================================================
ID    Property              Status Encoding schemes
===== ===================== ====== =================================================================================
1     Identifier            M      DOI (Digital Object Identifier) is preferred. The format should be “10.1234/foo”.
1.1   identifierType        M      Unlike DataCite, OpenAIRE allows for DOIs and other types of identifiers.
                                   Controlled List: Allowed values:
                                   ARK DOI Handle PURL URN URL
2     Creator               M
2.1   creatorName           M
2.2   nameIdentifier        M
2.2.1 nameIdentifierScheme  M
2.2.2 schemeURI             M
===== ===================== ====== =================================================================================

Access rights and license information
-------------------------------------

OpenAIRE uses the access rights to enable a better user experience by declaring the access rights clear and explicit in the portal. Access rights are specified using the 16. Rights property. Please see encoding scheme in the section above.

An example:

.. code-block:: xml
   :linenos:

   <rightsList>
    <rights rightsURI=”info:eu-repo/semantics/openAccess” />
   </rightsList>

OpenAIRE further recommends including license information if available:

.. code-block:: xml
   :linenos:

   <rightsList>
    <rights rightsURI=”info:eu-repo/semantics/openAccess” />
    <rights rightsURI=”http://creativecommons.org/licenses/by/4.0/”>
      Creative Commons Attribution 4.0 International
    </rights>
   </rightsList>

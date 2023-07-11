# Problem Statement 

Representation powers and mandates are an essential element for businesses establishing relationships with other businesses, governments and customers, because in many cases natural persons act on behalf of legal persons and depending on the sensitivity of the involved data/processes the Relying Party wants to enforce a high level of compliance and reduce associated legal risks.

The "traditional" way to solve this is by using manual processes and paper/PDF documents associated to onboarding and Know-Your-Customer (KYC) processes, that the Relying Party verifies until it is satisfied with the level of legal risk assumed when allowing a Principal to access some services on behalf of the Participant. Those setup processes are normally cumbersome, slow and people-intensive, creating a lot of friction in the initial stages of using a service, especially when strong identification is required by the nature of the service.

Verifiable Credentials can become a good instrument to migrate those paper/PDF documents to a machine-readable and legally-binding format and streamline and automate most of the tasks in this area, making the whole process more efficient while maintaining the same level of compliance and legal risk than with traditional processes.

Electronic powers of representation and mandates are an **explicit objective of the European Digital Identity Wallet** (EDIW) and the [proposed amendment to eIDAS](https://www.europarl.europa.eu/doceo/document/A-9-2023-0038_EN.html) to support it:

> To achieve simplification and cost reduction benefits to persons and businesses across the Union, including by enabling **powers of representation and e-mandates**, Member States should issue EDIWs relying on common standards and technical specifications to ensure seamless interoperability and to adequately increase the IT security, strengthen robustness against cyber-attacks and thus significantly reduce the potential risks of ongoing digitalisation for citizens and businesses.

However, currently there are important barriers that hinder the adoption of an EU wide solution for cross-border transfer of representation information, being one of the most relevant the **lack of a common semantic framework**. 

Representation is complex, and electronic mandates schemes and policies are basically national and usually do not contemplate the possibility to use those mandates in cross-border scenarios. The problem of mandates when accessing services from a Public Administration is extremely complex, so we will focus here on the private sector: when both the Relying Party and the Participant are legal persons from the private sector.

In order to have a usable mechanism using Verifiable Credentials, the main requirements are the following:

- **REQ-01**: **The credential is an e-mandate**, by embedding authorisation information in the credential and binding it to the identities of the issuer and subject. We call such a credential a Verifiable Authorisation.
  
  We need to define a controlled vocabulary that can be used to express in a formal language (e.g. ODRL) the semantics of the powers delegated to a Principal by the Participant.

- **REQ-02**: **The Relying Party does not have to know in advance the Principal** accessing its services on behalf of a Participant.

  However, the Relying Party should have an easy authentication mechanism based on Verifiable Credentials to ensure that the entity accessing the services is the same entity identified in the e-mandate, and so that it has the required powers to access.

  Ideally, to simplify the authentication and authorisation process for the Relying Party, the same credential that is a mandate (we call it a Verifiable Authorisation) can enable authentication (we call it a VerifiableID). Of course, we could use different credentials and even a "traditional" authentication mechanism, but having a single credential that can be used both for authentication and authorisation (using the powers specified in the mandate) is what we describe here.

- **REQ-03**: There may be several Principals accessing the services of a Relying Party on behalf of the same Participant, and each Principal may have different powers that enable them to access different (possibly overlapping) sets of services.

  The Relying Party specifies the powers that need to be validated for each service (the scope the access is requested on and the type of representation that the Service provider allows). Each individual service may require different sets of powers, at the sole discretion of the Relying Partly (of course always in synch with the agreement formalised with the Participant).
    
  The Participant grants the authorisations to the Principals at its own discretion. Only the Principals that have the powers required by an individual service can access that service. The Participant may have more powers than strictly required (for example, full representation of the legal entity).

- **REQ-04**: The Relying Party can **reduce the legal risks and associated costs of litigation** in court by leveraging the **presumption of non-repudiation** associated to the use of an eIDAS advanced/qualified seal/signature for the Verifiable Credential.

  Of course, the Relying Party is free to request from Participants other types of signatures, if it is willing to assume the higher level of legal risk. We define here a mechanism which can have the same level as a document with a handwritten signature (when using qualified electronic signatures/seals).

  In this way the credential is a **legally binding machine-readable document where the issuer (Participant) attests that it delegates the set of powers specified in the credential to the user identified as the subject of the credential (Principal)**.

- **REQ-05**: The Relying Party can verify that the issuer of the credential corresponds to a **real-world identity which is fully accountable** for the contents of the credential, without needing any additional third-party, trust framework or participant list associated to a given Data Space or Federation.

  Because we use an eIDAS signature/seal for the credential, the current EU legal and trust framework in place since 2016 is enough for the Relying Party to verify that the Participant has issued a legally-binding mandate to the Principal.

With all these properties, the credential is a **legally binding machine-readable document where the issuer attests that it delegates the set of powers specified in the credential to the user identified as the subject of the credential**. The subject can then **use the credential to authenticate to a Relying Party** because the identities of holder and subject are bound.

This mechanism leverages the eIDAS trust framework using advanced or qualified signatures and seals to provide a **high level of legal certainty and enjoying the presumption of non-repudiation in the courts**, something that does not happen when using other types of basic signatures.

The major missing item is the **controlled vocabulary [REQ-01]**, and even though the eIDAS2 initiative will eventually decide one within the supporting regulation, the Gaia-X community should define one ASAP to enable building interoperable ecosystems. Tracking the eIDAS2 initiative is important to be aligned, but we can not wait or depend on others doing that definition.

It may seem that just **[REQ-01]** is enough to implement an efficient e-mandate mechanism, but when implementing decentralised ecosystems which are based on Verifiable Credentials, having a mechanism implementing all of the requirements described above enables participants to reduce manual and cumbersome processes to the minimum, while maximising compliance to the legal framework.
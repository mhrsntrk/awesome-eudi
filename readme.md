# Awesome EUDI [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated resources for the European Digital Identity Wallet: the regulation, the Architecture and Reference Framework, the specifications underneath it, and the implementations that exist today.

The EUDI Wallet is the largest digital identity programme in the world by mandated population. Every EU member state must offer a wallet to its citizens, and the specifications it runs on (OpenID4VCI, OpenID4VP, SD-JWT VC, ISO mdoc) are being adopted well beyond Europe. The ecosystem is spread across dozens of repositories, four large-scale pilot consortia, several standards bodies and twenty-seven national implementations, with no single index. This list is that index.

Contributions are welcome. See [contributing.md](contributing.md) for what belongs here and how entries are written.

## Contents

- [Start Here](#start-here)
- [Regulation and Policy](#regulation-and-policy)
- [Architecture and Reference Framework](#architecture-and-reference-framework)
- [Specifications](#specifications)
- [Reference Implementation](#reference-implementation)
  - [Wallet Apps](#wallet-apps)
  - [Issuers, Verifiers and Services](#issuers-verifiers-and-services)
- [National Wallets](#national-wallets)
  - [Built in the Open](#built-in-the-open)
  - [National Programmes](#national-programmes)
- [Pilot Consortia](#pilot-consortia)
- [Independent Wallets and Toolkits](#independent-wallets-and-toolkits)
- [Libraries by Language](#libraries-by-language)
  - [Kotlin and JVM](#kotlin-and-jvm)
  - [Swift](#swift)
  - [JavaScript and TypeScript](#javascript-and-typescript)
  - [Python](#python)
  - [Rust](#rust)
- [Age Verification](#age-verification)
- [Testing and Conformance](#testing-and-conformance)
- [Trust Infrastructure](#trust-infrastructure)

## Start Here

- [EU Digital Identity Wallet Home](https://ec.europa.eu/digital-building-blocks/sites/spaces/EUDIGITALIDENTITYWALLET/pages/6944877) - The European Commission's landing page for the programme, linking specifications, releases and support channels.
- [Architecture and Reference Framework](https://eudi.dev/) - The ARF rendered as a browsable site. The single most important document in the ecosystem.

## Regulation and Policy

- [Regulation (EU) 2024/1183](https://eur-lex.europa.eu/eli/reg/2024/1183/oj) - The amending regulation that establishes the European Digital Identity Framework, commonly called eIDAS 2. The primary legal source.
- [EUDI Regulation policy page](https://digital-strategy.ec.europa.eu/en/policies/eudi-regulation) - Commission summary of obligations, timelines and member state duties, including the 2026 milestones.

## Architecture and Reference Framework

- [eudi-doc-architecture-and-reference-framework](https://github.com/eu-digital-identity-wallet/eudi-doc-architecture-and-reference-framework) - The ARF itself, versioned in the open with issues and discussions. Read the changelog between releases; requirements move.
- [eudi-doc-standards-and-technical-specifications](https://github.com/eu-digital-identity-wallet/eudi-doc-standards-and-technical-specifications) - Tracking and alignment of the standards the ARF depends on, including gap analysis.
- [eudi-doc-attestation-rulebooks-catalog](https://github.com/eu-digital-identity-wallet/eudi-doc-attestation-rulebooks-catalog) - Catalogue of attestation rulebooks defining what each credential type contains.

## Specifications

- [OpenID for Verifiable Credential Issuance](https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0.html) - How a wallet obtains a credential from an issuer. The issuance half of the stack.
- [OpenID for Verifiable Presentations](https://openid.net/specs/openid-4-verifiable-presentations-1_0.html) - How a verifier requests and receives a presentation. The presentation half.
- [SD-JWT (RFC 9901)](https://datatracker.ietf.org/doc/rfc9901/) - Selective Disclosure JWT, the mechanism that lets a holder reveal individual claims.
- [SD-JWT VC](https://datatracker.ietf.org/doc/draft-ietf-oauth-sd-jwt-vc/) - The credential format built on SD-JWT, and one of the two formats the ARF mandates.
- [ISO/IEC 18013-5](https://www.iso.org/standard/69084.html) - The mobile driving licence standard behind the mdoc format, the other mandated format.
- [OpenID4VC High Assurance Interoperability Profile](https://github.com/openid/OpenID4VC-HAIP) - The profile that pins down the optionality in OID4VCI and OID4VP so implementations actually interoperate.
- [Token Status List](https://datatracker.ietf.org/doc/draft-ietf-oauth-status-list/) - Revocation and suspension status for credentials without phoning home per check.
- [W3C Verifiable Credentials Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/) - The W3C model, present in the wider ecosystem though not the ARF's primary format.
- [ETSI TS 119 612](https://www.etsi.org/deliver/etsi_ts/119600_119699/119612/) - Trusted lists, the format that carries who is authorised to issue and to verify.

## Reference Implementation

The European Commission publishes a complete reference stack. It is the fastest way to see a working issuer, wallet and verifier talking to each other.

### Wallet Apps

- [eudi-app-android-wallet-ui](https://github.com/eu-digital-identity-wallet/eudi-app-android-wallet-ui) - The Android reference wallet.
- [eudi-app-ios-wallet-ui](https://github.com/eu-digital-identity-wallet/eudi-app-ios-wallet-ui) - The iOS reference wallet.
- [eudi-app-multiplatform-verifier-ui](https://github.com/eu-digital-identity-wallet/eudi-app-multiplatform-verifier-ui) - Multiplatform verifier application.

### Issuers, Verifiers and Services

- [eudi-srv-pid-issuer](https://github.com/eu-digital-identity-wallet/eudi-srv-pid-issuer) - PID and mDL issuer microservice following OpenID4VCI.
- [eudi-srv-web-issuing-eudiw-py](https://github.com/eu-digital-identity-wallet/eudi-srv-web-issuing-eudiw-py) - Python issuer backend for PID, mDL and other attestations.
- [eudi-srv-verifier-endpoint](https://github.com/eu-digital-identity-wallet/eudi-srv-verifier-endpoint) - Backend service acting as a verifier or relying party endpoint.
- [eudi-web-verifier](https://github.com/eu-digital-identity-wallet/eudi-web-verifier) - Web front end for the verifier endpoint.
- [eudi-srv-wallet-provider](https://github.com/eu-digital-identity-wallet/eudi-srv-wallet-provider) - Wallet provider service implementing wallet attestation.
- [eudi-srv-web-relyingparty-registration-py](https://github.com/eu-digital-identity-wallet/eudi-srv-web-relyingparty-registration-py) - Relying party registration service, the piece that decides who may ask for what.

## National Wallets

Member states are at very different stages. Some are developing in public, most are not. Both are listed, because knowing that a country's work is closed is itself useful.

### Built in the Open

- [nl-wallet](https://github.com/MinBZK/nl-wallet) - The Netherlands' public wallet, developed in the open by the Ministry of the Interior. One of the most complete national implementations.
- [wallet-app-android](https://github.com/diggsweden/wallet-app-android) - Sweden's national wallet for Android, developed by DIGG and updated daily.
- [wallet-app-ios](https://github.com/diggsweden/wallet-app-ios) - The iOS counterpart of Sweden's national wallet.
- [wallet-provider](https://github.com/diggsweden/wallet-provider) - Sweden's wallet provider service, issuing wallet unit attestations.
- [eid-wallet-it-docs](https://github.com/italia/eid-wallet-it-docs) - Italy's national wallet technical specifications, published as a versioned book.
- [valera](https://github.com/a-sit-plus/valera) - Austrian wallet app built on the A-SIT Plus credential stack.
- [BMI eIDAS2 workspace](https://gitlab.opencode.de/bmi/eudi-wallet/eidas2) - Germany's Federal Ministry of the Interior working in the open on OpenCoDE, including the public consultations behind the national architecture.
- [irmamobile](https://github.com/privacybydesign/irmamobile) - Yivi, formerly IRMA, the long-running Dutch attribute-based credential wallet that predates the ARF and informs it.
- [swiyu-issuer](https://github.com/swiyu-admin-ch/swiyu-issuer) - Generic issuer for the Swiss e-ID trust infrastructure. Switzerland is outside the EU, but swiyu runs the same OpenID4VC stack and is unusually well documented.
- [swiyu-verifier](https://github.com/swiyu-admin-ch/swiyu-verifier) - The verifier half of the Swiss infrastructure.
- [swiyu documentation](https://swiyu-admin-ch.github.io/) - Full public documentation for the Swiss trust infrastructure, worth reading regardless of jurisdiction.

### National Programmes

Official programme pages for wallets with no public source code yet. Useful for tracking timelines, pilots and procurement.

- [SPRIND EUDI Wallet](https://www.sprind.org/en/actions/strategic-projects/eudi-wallet) - Germany's national wallet project, run through the federal innovation agency.
- [SPRIND Funke EUDI Wallet Prototypes](https://www.sprind.org/en/actions/challenges/eudi-wallet-prototypes) - The prototype competition that shaped the German approach, with results released openly.
- [France Identité](https://france-identite.gouv.fr/) - France's national identity app, live in production and on the path to EUDI certification.
- [Cartera Digital](https://carteradigital.gob.es/) - Spain's national wallet programme.
- [mObywatel](https://www.mobywatel.gov.pl/) - Poland's citizen wallet, one of the most widely used national identity apps in Europe.
- [gov.gr Wallet](https://wallet.gov.gr/) - Greece's wallet, an early mover on national ID and driving licence in a phone.
- [eDoklady](https://edoklady.gov.cz/) - Czechia's digital documents app.
- [AltID](https://www.borger.dk/hjaelp-og-vejledning/hvad-har-du-brug-for-hjaelp-til/altid) - Denmark's official ID app from the Danish Agency for Digitisation, holding an identity card and a standalone age credential. Credentials stay on the device, it does not replace MitID, and it is Denmark-only until EU-wide use arrives.
- [DIGG](https://www.digg.se/) - The Swedish agency behind the repositories above, and the place its roadmap is published.

## Pilot Consortia

The large-scale pilots are where the ARF meets real use cases. Their outputs are often more concrete than the framework itself.

- [EWC eudi-wallet-rfcs](https://github.com/EWC-consortium/eudi-wallet-rfcs) - The EU Digital Identity Wallet Consortium's RFCs, the most readable set of implementation profiles in the ecosystem.
- [POTENTIAL](https://www.digital-identity-wallet.eu/) - The largest pilot, covering government services, banking, telecoms, driving licences and health.
- [NOBID](https://www.nobidconsortium.com/) - The Nordic-Baltic pilot, focused on payments.
- [DC4EU](https://www.dc4eu.eu/) - Pilot covering education credentials and social security coordination.
- [APTITUDE wallet specifications](https://github.com/APTITUDE-Consortium/aptitude-eudi-wallet-specs) - Specifications from the APTITUDE consortium.

## Independent Wallets and Toolkits

- [waltid-identity](https://github.com/walt-id/waltid-identity) - All-in-one issuer, verifier and wallet toolkit with hosted and self-hosted options.
- [one-wallet](https://github.com/procivis/one-wallet) - The wallet application built on one-core.
- [AltMe](https://github.com/TalaoDAO/AltMe) - Open-source wallet supporting EBSI, ARF and DIIP profiles.
- [eudiplo](https://github.com/openwallet-foundation/eudiplo) - Integration layer that fronts EUDI issuance and verification for services that do not want to implement the protocols themselves.
- [sprucekit-mobile](https://github.com/spruceid/sprucekit-mobile) - Libraries and examples for adding verifiable credentials and mDL to mobile apps.

## Libraries by Language

### Kotlin and JVM

- [eudi-lib-jvm-openid4vci-kt](https://github.com/eu-digital-identity-wallet/eudi-lib-jvm-openid4vci-kt) - OpenID4VCI in Kotlin, wallet role.
- [eudi-lib-jvm-openid4vp-kt](https://github.com/eu-digital-identity-wallet/eudi-lib-jvm-openid4vp-kt) - OpenID4VP in Kotlin, wallet role.
- [eudi-lib-jvm-sdjwt-kt](https://github.com/eu-digital-identity-wallet/eudi-lib-jvm-sdjwt-kt) - Issuing and verifying SD-JWT on the JVM.
- [eudi-lib-android-wallet-core](https://github.com/eu-digital-identity-wallet/eudi-lib-android-wallet-core) - Core wallet logic for Android, the layer beneath the reference app.
- [eudi-lib-android-verifier-core](https://github.com/eu-digital-identity-wallet/eudi-lib-android-verifier-core) - Android SDK for verifying documents, ISO 18013-5 compliant.
- [eudi-lib-kmp-statium](https://github.com/eu-digital-identity-wallet/eudi-lib-kmp-statium) - Token Status List checking for Kotlin Multiplatform.
- [vck](https://github.com/a-sit-plus/vck) - Kotlin Multiplatform library implementing the W3C model, SD-JWT and ISO 18013-5.
- [multipaz](https://github.com/openwallet-foundation/multipaz) - ISO mdoc and OpenID4VC libraries from the OpenWallet Foundation, formerly the Google Identity Credential codebase.

### Swift

- [eudi-lib-ios-wallet-kit](https://github.com/eu-digital-identity-wallet/eudi-lib-ios-wallet-kit) - The Commission's iOS wallet kit, the layer beneath the reference app.
- [eudi-lib-ios-openid4vci-swift](https://github.com/eu-digital-identity-wallet/eudi-lib-ios-openid4vci-swift) - OpenID4VCI in Swift, wallet role.
- [eudi-lib-ios-openid4vp-swift](https://github.com/eu-digital-identity-wallet/eudi-lib-ios-openid4vp-swift) - OpenID4VP in Swift, wallet role.
- [eudi-lib-sdjwt-swift](https://github.com/eu-digital-identity-wallet/eudi-lib-sdjwt-swift) - SD-JWT issuance and verification in Swift.
- [eudi-lib-ios-iso18013-data-model](https://github.com/eu-digital-identity-wallet/eudi-lib-ios-iso18013-data-model) - The mdoc data model for iOS.
- [eudi-lib-ios-iso18013-data-transfer](https://github.com/eu-digital-identity-wallet/eudi-lib-ios-iso18013-data-transfer) - ISO 18013-5 proximity data transfer for iOS.
- [JWSETKit](https://github.com/amosavian/JWSETKit) - General JWS, JWE and JWT toolkit for Apple platforms, useful underneath credential work.

### JavaScript and TypeScript

- [credo-ts](https://github.com/openwallet-foundation/credo-ts) - TypeScript framework for building wallets, issuers and verifiers, with OpenID4VC modules.
- [sd-jwt-js](https://github.com/openwallet-foundation/sd-jwt-js) - Reference JavaScript implementation of SD-JWT.
- [OID4VC](https://github.com/Sphereon-Opensource/OID4VC) - Sphereon's OpenID4VC libraries for issuance and presentation.
- [SSI-SDK](https://github.com/Sphereon-Opensource/SSI-SDK) - Broader SSI toolkit, now legacy but still widely deployed.

### Python

- [eudi-wallet-it-python](https://github.com/italia/eudi-wallet-it-python) - Toolchain for an OpenID4VP relying party with a SATOSA backend, following the Italian profile.
- [pyMDOC-CBOR](https://github.com/IdentityPython/pyMDOC-CBOR) - ISO mdoc CBOR issuer and verifier for PID and mDL use cases.

### Rust

- [one-core](https://github.com/procivis/one-core) - Credential engine covering the mandated formats.
- [eudi-rust-core](https://github.com/blockhousetech/eudi-rust-core) - Rust building blocks for EUDI wallet components.
- [openid4vc](https://github.com/impierce/openid4vc) - Rust implementation of the OpenID4VC family.

## Age Verification

The EU age verification app is a separate programme built on the same stack, and it is the first place most citizens will meet a wallet-style credential.

- [av-doc-technical-specification](https://github.com/eu-digital-identity-wallet/av-doc-technical-specification) - Technical specification for the European age verification solution.
- [av-app-android-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-android-wallet-ui) - Android age verification app.
- [av-app-ios-wallet-ui](https://github.com/eu-digital-identity-wallet/av-app-ios-wallet-ui) - iOS age verification app.
- [av-lib-ios-w3c-dc-api](https://github.com/eu-digital-identity-wallet/av-lib-ios-w3c-dc-api) - W3C Digital Credentials API support for the iOS app.

## Testing and Conformance

- [OpenID Conformance Suite](https://www.certification.openid.net/) - Official certification tooling for OpenID4VCI and OpenID4VP implementations.
- [eudi-doc-functional-conformance-assessment](https://github.com/eu-digital-identity-wallet/eudi-doc-functional-conformance-assessment) - The Commission's functional conformance methodology.
- [eudi-doc-testing-application](https://github.com/eu-digital-identity-wallet/eudi-doc-testing-application) - End-to-end functional tests for the reference wallet.
- [credimi](https://github.com/ForkbombEu/credimi) - Conformance and interoperability checking for credential implementations.
- [wp4-interop-test-bed](https://github.com/webuild-consortium/wp4-interop-test-bed) - Cross-implementation interoperability test bed.

## Trust Infrastructure

- [EU Trusted List Browser](https://eidas.ec.europa.eu/efda/tl-browser/) - Browse the trusted lists that decide which providers are qualified.
- [eudi-srv-trust-validator](https://github.com/eu-digital-identity-wallet/eudi-srv-trust-validator) - Service that validates an entity's certificate against ETSI 119 612 trusted lists.
- [eudi-lib-kmp-etsi-1196x2](https://github.com/eu-digital-identity-wallet/eudi-lib-kmp-etsi-1196x2) - Certificate chain verification against ETSI trusted lists, for use inside a wallet.

## Related Lists

- [awesome-self-sovereign-identity](https://github.com/animo/awesome-self-sovereign-identity) - Broader SSI list covering the pre-EUDI decentralised identity world.
- [best-of-digital-identity](https://github.com/jruizaranguren/best-of-digital-identity) - Automatically ranked list of digital identity open-source projects.

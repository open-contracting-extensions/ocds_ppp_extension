# OCDS for Public Private Partnerships

The Open Contracting Data Standard for Public Private Partnerships profile provides an extended Open Contracting Data Standard schema, offering a structured data model for presenting information on Public Private Partnership Projects.

It is based on the [World Bank Framework for Disclosure in Public Private Partnership Projects](http://www.worldbank.org/en/topic/publicprivatepartnerships/brief/ppp-tools#T1) and was developed between May 2016 and May 2017 through a partnership between the [World Bank Open Contracting team](https://blogs.worldbank.org/category/tags/open-contracting), [PPP team](http://www.worldbank.org/en/topic/publicprivatepartnerships), [Open Contracting Partnership](http://open-contracting.org), and [Open Data Services Co-operative](http://www.opendataservices.coop).

Full documentation of the profile is available at [http://standard.open-contracting.org/profiles/ppp/](http://standard.open-contracting.org/profiles/ppp/)

The consolidated OCDS for PPPs extension can be declared in [OCDS package metadata](http://standard.open-contracting.org/latest/en/schema/release_package/) using:

```json
{
  "extensions": [
    "http://standard.open-contracting.org/profiles/ppp/extension/1__0__0__beta/extension.json"
  ],
  "releases": []
}
```

## About PPP extensions

OCDS for PPPs is constructed from [a number of different modular extensions to OCDS](http://standard.open-contracting.org/profiles/ppp/latest/en/extensions/), most of which can be used independently from the profile.

This repository contains one additional extension that forms part of the OCDS for PPPs profile. This extension introduces a number of fields and building blocks that are specific to PPP disclosure against the World Bank Framework.

### PPP Specific extensions

#### Evaluation Indicators

The PPP disclosure framework calls for a number of different indicators to be reported relating to governments evaluation of a PPP project.

The `awards.evaluationIndicators` section includes fields to express the **value** and supporting **free-text details** for each indicator:

* discountRate
* riskPremium
* netPresentValue

##### Example

```
"evaluationIndicators": {
  "riskPremium": 0.0092,
  "riskPremiumDetails": "Based on a market risk premium of 6.0% (per government guidelines) and an asset beta of 0.45 (per a sample of listed telecommunication network providers) the project risk allocation gives rise to a risk premium of 0.92%",
  "discountRate": 0.03,
  "discountRateDetails": "Based on the current long term public sector bond rate",
  "netPresentValue": {
    "amount": 118044591901.35034,
    "currency": "USD"
  }
```

#### Finance Summary

The PPP disclosure framework calls for a number of different indicators relating to the financial model of a PPP project. Whilst some of these may be reported as metrics on an ongoing basis, some are simple single values.

The `contracts.financeSummary` section includes fields to express the **value** and supporting **free-text details** for each indicator:

* debtEquityRatio
* shareCapital
* subsidyRatio
* projectIRR

##### Example

```
"financeSummary": {
  "debtEquityRatio": 2.05,
  "debtEquityRatioDetails": "Until the target population coverage is reached mega Consortium must comply with a contribution of capital of at least 30% of the total value of the company",
  "shareCapital": {
    "amount": 20000000,
    "currency": "USD"
  }
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2023-06-07

* Remove unused `+partyRole.csv` codes:
  * consortiaMember
  * grantor
  * notary
  * otherWitness
  * socialWitness

### 2021-04-19

* Replace `documentType.csv` with `+documentType.csv`, which adds new codes instead of replacing the codelist.

### 2021-02-15

* Restore 'procuringEntity', 'tenderer' and 'funder' roles. Remove 'bidder' role.

### 2021-01-14

* Remove `+releaseTag.csv` codelist.

### 2021-01-11

* Remove `initiationType.csv` codelist.
* Restore `buyer` and `awards.suppliers` fields.

### 2020-11-16

* Restore deprecated fields.
* Restore `Budget.project` and `Budget.projectID` fields.

### 2020-06-04

* Review normative and non-normative words.

### 2020-04-24

* Add `minProperties`, `minItems` and/or `minLength` properties.

### 2019-05-01

* Remove 'qualifiedBidder' and 'disqualifiedBidder' codes from `+partyRole.csv` (moved to [qualification](https://github.com/open-contracting-extensions/ocds_qualification_extension) extension).

### 2019-03-20

* Set `"uniqueItems": true` on array fields.

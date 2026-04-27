# Fashion & Apparel E-Commerce Ontology (FashionO)

## Project Overview
The Fashion & Apparel E-Commerce Ontology (FashionO) provides a shared vocabulary for fashion products sold online. The ontology holds knowledge about products, brands, materials, colors, sizes, seasons, and styles, allowing users to search and filter products using specific criteria.

## Ontology Requirements Specification (ORSD)
This project follows a formal specification to ensure all functional and non-functional requirements are met.

### 1. Purpose and Scope
* **Purpose**: To provide a shared vocabulary for fashion products sold online, supporting search and filtering by specific criteria like material, gender, or price range.
* **Scope**: Focuses on fashion products and their attributes (clothing, footwear, accessories, brands, materials, colors, sizes, seasons, styles, and collections). It also covers the basic commerce layer including product listings, reviews, customers, and orders.
* **Out of Scope**: Payment processing, shipping, and logistics are not covered.

### 2. Functional Requirements (Competency Questions)
The ontology is designed to answer specific business and user questions, including:
* Which products belong to a specific category such as Dresses or Sneakers?
* Which products are made of a specific material such as Cotton or Silk?
* What is the price range of products from a specific brand?
* Which products have an average customer rating above 4.0?
* Which products are appropriate for a specific season such as Winter?

### 3. Non-Functional Requirements
* **Implementation Language**: Web Ontology Language — OWL 2 DL, written in Turtle (.ttl) format.
* **Reuse**: Reuses terms from schema.org and GoodRelations where possible.
* **Licensing**: Released under Creative Commons CC BY 4.0 license.
* **Versioning**: Uses semantic versioning starting from version 1.0.0.

---

## Technical Implementation
* **TBox**: Defines the terminological framework, including class hierarchies and relationships between attributes.
* **ABox**: Contains individuals and assertions representing real-world data like specific products, brands, and customer reviews.
* **Inference**: Supports reasoning to answer complex queries, such as identifying products that fit multiple filter criteria simultaneously.

---

## Sample SPARQL Query
Below is a sample query used to verify products belonging to a specific category from a specific brand:

```sparql
PREFIX fashiono: <http://w3id.org/fashion#>
SELECT ?productName ?price
WHERE {
    ?product a fashiono:TopWear ;
             fashiono:productName ?productName ;
             fashiono:hasBrand fashiono:BrandZara ;
             fashiono:hasListing/fashiono:price ?price .
}
```

---

## Repository Structure
* **ontology/**: Contains the TBox.ttl schema file.
* **data/**: Contains the ABox.ttl instance data.
* **docs/**: Contains the formal ORSD documentation.
* **queries/**: Collection of SPARQL queries for testing competency questions.

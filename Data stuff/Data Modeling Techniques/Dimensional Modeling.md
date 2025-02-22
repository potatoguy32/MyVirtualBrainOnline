Dimensional Modeling (DM), integral to the Kimball DW and BI Lifecycle Methodology, also known as Business Dimensional Lifecycle methodology, was developed by Ralph Kimball. It encompasses a suite of methods, techniques, and concepts essential for Data Warehouse design.
This approach emphasizes identifying and modeling key business processes initially and then progressively adding more processes. This bottom-up strategy contrasts with Inmon’s top-down approach, which involves designing an enterprise-wide data model using [[Entity-Relationship Modeling]] (ER) and other tools.

## Key components
- Facts: Measurable data elements that represent the business metrics of interest.
- Dimensions: Descriptive data elements that are used to categorize the data.
- Attributes: Characteristics of dimension use to filter, search facts, etc.
- Fact table: In a dimensional data model, the fact table is the central table that contains the measures or metrics of interest, surrounded by the dimension tables that describe the attributes of the measures. The dimension tables are related to the fact table through foreign key relationships
- Dimension table: Dimensions of a fact are mentioned by the dimension table and they are basically joined by a foreign key. Dimension tables are simply de-normalized tables. The dimensions can be having one or more relationships.

## Use cases
- Information is structured following domain areas.
- Complementary information is constantly being added and additional insights need to be reported.

## Example

![[Pasted image 20250119112805.png]]
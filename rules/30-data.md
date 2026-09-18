# Data Rules

## Data contracts

Data exchanged between components must have an explicit schema.

Prefer versioned contracts for externally consumed data.

## Validation

Validate data at system boundaries.

Do not assume upstream data is correct.

## Nullability

Model optional/null fields explicitly.

Do not silently convert missing values into zero, empty strings, or false unless that is a documented business rule.

## Time

Store timestamps with explicit timezone semantics.

Do not mix local time and UTC implicitly.

## Data lineage

For important financial or regulatory data, maintain lineage from:

source -> ingestion -> transformation -> storage -> output/report.

## Reproducibility

Important transformations should be reproducible from recorded inputs, configuration, and code version where practical.

## Data quality

Detect and record:

- missing data;
- duplicates;
- invalid formats;
- out-of-range values;
- unexpected schema changes.

## Regulatory/reporting data

For regulatory reporting, retain sufficient source and transformation metadata to explain how an output value was produced.

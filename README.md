# EHRS Functional model - Record Lifecycle Events
Split from the core FHIR specification on May 9, 2022.

# To build IG
(optional)> curl -L https://github.com/HL7/fhir-ig-publisher/releases/latest/download/publisher.jar -o publisher.jar
> java -jar publisher.jar -ig ig.ini

N.B. publisher 1.2.42 fails with:
> Jekyll has failed. Complete output from running Jekyll:   Liquid Exception: Could not locate the included file 'StructureDefinition-ehrsrle-auditevent-sd-xref.xhtml' in any of ["/home/michael/eclipse-workspace/EHRSFM/ehrs-rle-ig/temp/pages/_includes"]. Ensure it exists in one of those directories and, if i (01:03.819)
> Note: Check that Jekyll is installed correctly                                   (01:03.820)

# Builds status
https://fhir.github.io/auto-ig-builder/builds.html

# Validate FHIR
(optional)> curl -L https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar -o validator_cli.jar
> java -jar ~/eclipse-workspace/latest-ig-publisher/validator_cli.jar -version 5.0.0 input/examples/AuditEvent-Example-1.json
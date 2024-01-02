# EHRS Functional model - Record Lifecycle Events
Split from the core FHIR specification on May 9, 2022.

CI build https://build.fhir.org/ig/HL7/ehrs-rle-ig/branches/main/index.html

# To build IG
(optional)> curl -L https://github.com/HL7/fhir-ig-publisher/releases/latest/download/publisher.jar -o publisher.jar
> java -jar publisher.jar -ig ig.ini

N.B. If publisher fails, first clean package cache for R5
> rm -rf ~/.fhir/packages/hl7.fhir.r5.core#current
> rm -rf ~/.fhir/packages/hl7.fhir.r5.core#5.0.0

# Builds status
https://fhir.github.io/auto-ig-builder/builds.html

# Validate FHIR
(optional)> curl -L https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar -o validator_cli.jar
> java -jar validator_cli.jar -version 5.0.0 input/examples/AuditEvent-Example-1.json

# Trigger CI build
> curl -X POST  "https://us-central1-fhir-org-starter-project.cloudfunctions.net/ig-commit-trigger" \
  -H "Content-type: application/json" \
  --data '{"ref": "refs/heads/master", "repository": {"full_name": "HL7/ehrs-rle-ig"}}'
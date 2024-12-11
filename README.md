# EHRS Functional model - Record Lifecycle Events

* Split from the core FHIR specification on May 9, 2022.
* FHIR R6 (6.0.0-ballot2) Dec 11, 2024

CI build https://build.fhir.org/ig/HL7/ehrs-rle-ig/branches/main/index.html

# To build IG

> docker run --rm -it -v $(pwd):/home/publisher/ig hl7fhir/ig-publisher-base:latest
@> _updatePublisher.sh
@> _genonce.sh

# Builds status

https://fhir.github.io/auto-ig-builder/builds.html

# Validate FHIR

(optional)> curl -L https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar -o validator_cli.jar
> java -jar validator_cli.jar -version 5.0.0 input/examples/AuditEvent-Example-1.json

# Trigger CI build

> curl -X POST  "https://us-central1-fhir-org-starter-project.cloudfunctions.net/ig-commit-trigger" \
  -H "Content-type: application/json" \
  --data '{"ref": "refs/heads/master", "repository": {"full_name": "HL7/ehrs-rle-ig"}}'
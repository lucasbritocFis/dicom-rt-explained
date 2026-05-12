
# Anonymization guidelines for sample DICOMs

Any DICOM contributed to this repository must be anonymized before submission.

## Minimum required removals

- (0010,0010) Patient Name → "TEST^PATIENT"
- (0010,0020) Patient ID → "TEST001"
- (0010,0030) Patient Birth Date → "19700101"
- (0008,0080) Institution Name → "TEST_INSTITUTION"
- (0008,0090) Referring Physician Name → ""
- (0008,1060) Name of Physician(s) Reading Study → ""
- All Study Date / Series Date / Acquisition Date → "19700101"

## Recommended tool

Use `pydicom-anonymizer` or the official `dcmtk` `dcmodify` utility.
A reference Python script will be added under `examples/` once the project is local-runnable.

## Disclaimer

Verifying anonymization is the responsibility of the contributor. The
maintainer of this repository will reject any PR where Patient Name or
Patient ID fields appear non-anonymized.

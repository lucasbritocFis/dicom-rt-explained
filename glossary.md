
# Glossary — Radiation Oncology and DICOM-RT

Plain-language definitions for the acronyms that appear constantly in DICOM-RT.

## Anatomy / Targets

- **GTV** — Gross Tumor Volume. The visible tumor on imaging.
- **CTV** — Clinical Target Volume. GTV plus a margin for microscopic spread.
- **PTV** — Planning Target Volume. CTV plus a setup uncertainty margin.
- **OAR** — Organ at Risk. An organ near the target that should receive minimal dose.

## Dose

- **Gy** — Gray. The SI unit of absorbed dose. 1 Gy = 1 joule of radiation energy per kilogram of tissue.
- **cGy** — Centigray. 1/100 of a Gray. Still common in older systems.
- **Prescription dose** — The dose intended to be delivered to the target.
- **Fraction** — One daily treatment session. A 60 Gy prescription over 30 fractions = 2 Gy per fraction.
- **DVH** — Dose Volume Histogram. The standard summary of how much dose each structure received.

## Techniques

- **3D-CRT** — Three-Dimensional Conformal Radiotherapy. Static beams shaped by the MLC to the target.
- **IMRT** — Intensity-Modulated Radiotherapy. Multiple beams with varying intensity within each beam to better conform dose.
- **VMAT** — Volumetric Modulated Arc Therapy. IMRT delivered with continuously rotating gantry arcs.
- **SBRT** — Stereotactic Body Radiotherapy. High-precision treatment in few fractions (typically 3-5).
- **SRS** — Stereotactic Radiosurgery. Single-fraction stereotactic brain treatment.
- **DIBH** — Deep Inspiration Breath Hold. Patient holds breath during treatment to move organs away from target (mainly left-breast).

## Equipment

- **Linac** — Linear accelerator. The machine that produces the treatment beam.
- **MLC** — Multi-Leaf Collimator. The set of tungsten leaves inside the linac head that shapes the beam.
- **MU** — Monitor Unit. The dose output of the linac, calibrated such that 1 MU delivers a known dose under reference conditions.
- **EPID** — Electronic Portal Imaging Device. The flat-panel imager on the opposite side of the patient from the linac source.
- **CBCT** — Cone Beam Computed Tomography. 3D imaging acquired on the linac itself, used for patient setup verification.

## Software systems

- **TPS** — Treatment Planning System. Software where the plan is designed (Eclipse, RayStation, Monaco, Pinnacle).
- **OIS** — Oncology Information System. The clinical workflow system (ARIA, MOSAIQ).
- **R&V** — Record-and-Verify system. Subsystem that ensures the linac delivers what was planned.

## DICOM-specific

- **SOP Instance UID** — Unique identifier for a single DICOM object instance.
- **Series Instance UID** — Unique identifier for a series of related DICOM objects (e.g., a CT scan's slices).
- **Frame of Reference UID** — Identifies a shared geometric coordinate system across multiple objects.
- **Transfer Syntax** — How a DICOM object is encoded for transmission (compression, byte order, etc.).
- **IOD** — Information Object Definition. A class of DICOM object (RT Plan is one IOD, RT Dose is another).

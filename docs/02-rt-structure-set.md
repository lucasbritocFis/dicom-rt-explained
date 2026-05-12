
# RT Structure Set

## What you'll learn
- What contours are and why they exist as a separate DICOM object
- The two halves of an RT Structure Set: the names/types vs the geometric points
- How to extract: structure names, volumes, slice contours
- ROI types: TARGET, ORGAN, EXTERNAL, AVOIDANCE
- TG-263 nomenclature reality vs ideal

## 1. Clinical meaning

## 2. The two halves

The RT Structure Set has a curiously bifurcated structure that confuses developers on first contact:

### Half 1: Structure Set ROI Sequence (3006,0020)
The "definitions" — each ROI has a name, an ID, and which Frame of Reference it lives in.

### Half 2: ROI Contour Sequence (3006,0039)
The actual geometric points — for each ROI ID, the polylines on each CT slice.

To get the full picture of one structure (name + contours), you have to join the two sequences by ROI Number.

## 3. The third half: RT ROI Observations Sequence (3006,0080)
The "metadata" — what type is this ROI (TARGET / ORGAN / EXTERNAL / etc.), what's its interpreted type, what's its physical property.

Every well-formed RT Structure Set has all three sequences. Each refers to the others by ROI Number.

## 4. Tags by question

### "What structures are in this file?"
[continuar]

### "What are the targets?"


### "What are the organs at risk?"


### "What are the geometric contour points for X?"


## 5. Pitfalls
- Same structure may have multiple aliases across TPS (PTV_70, PTV70, PTV70Gy, PTV_7000cGy)
- TG-263 nomenclature is a recommendation, not enforced — real data is messy
- Empty structures (defined but no contours) — happen when planner deletes contours but not the structure entry
- Non-contiguous contours — a structure can have gaps between CT slices
- 2D vs 3D contour representation — Contour Geometric Type varies

## See also
- [TG-263 nomenclature standard](https://www.aapm.org/pubs/reports/RPT_263.pdf)
- [RT Plan](01-rt-plan.md) — references this structure set
- [RT Dose](03-rt-dose.md) — uses these structures to compute DVH

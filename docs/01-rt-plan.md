
# RT Plan

## What you'll learn
- What an RT Plan represents clinically
- The most useful tags, organized by what they answer
- How to extract: prescription, technique, beams, MUs, machine
- Common variations (3D-CRT vs IMRT vs VMAT representation)
- Pitfalls when reading plans from different TPS

## 1. Clinical meaning


## 2. The skeleton — high-level structure
[Diagrama mental:
- Plan Header (label, intent, status, date)
- Dose Reference Sequence (prescription)
- Fraction Group Sequence (how the prescription is broken into fractions)
- Beam Sequence (the actual beams)
- Patient Setup (positioning)
- Tolerance Tables (limits for delivery)
]

## 3. Tags by question — "what does the plan say about X?"

### "What's the prescription?"
- (300A,0010) Dose Reference Sequence
  - (300A,0014) Dose Reference Structure Type
  - (300A,0026) Target Prescription Dose
[continuar com cada tag]

### "How is it fractionated?"
- (300A,0070) Fraction Group Sequence
  - (300A,0078) Number of Fractions Planned
  - (300A,0080) Number of Fraction Group
[continuar]

### "How many beams, and what kind?"
[continuar]

### "What machine is this for?"
- (300A,00B2) Treatment Machine Name
- (0008,1090) Manufacturer Model Name
[continuar]

### "What's the isocenter?"
- (300A,012C) Isocenter Position (within Control Point Sequence)
[continuar]

### "Is this IMRT or VMAT or 3D-CRT?"
[Explicar como inferir a técnica a partir do Beam Sequence, Control Points, MLC behavior — esta é a pergunta mais frequente]

## 4. Extracting basic information — code example
[Quando você estiver em casa, adicionar bloco Python rodável aqui]

## 5. Pitfalls
- VMAT vs IMRT representation differences
- Multiple plans referenced by same structure set
- Plan Status field — "APPROVED" vs "UNAPPROVED" — sometimes treatment records exist for "UNAPPROVED" plans (clinical workaround, regulatory edge case)
- Patient Position tag — HFS, HFP, FFS, FFP — matters for coordinate interpretation
- TPS-specific quirks: Eclipse emits X, RayStation emits Y, etc. [list known ones]

## See also
- [RT Structure Set](02-rt-structure-set.md) — what this plan was made against
- [RT Dose](03-rt-dose.md) — what this plan calculates dose for

# Hippocampal TI Stimulation — Optimising Memory Consolidation via Temporal Interference

> **Archived research project · Documentation only · No code included**

**MEng Individual Research Project — King's College London, May 2025**
Supervisor: Dr. Ines Violante

---

## Overview

Memory consolidation — the process by which new memories become stable — occurs primarily during slow-wave sleep, when the hippocampus reactivates recent experiences and integrates them into long-term cortical storage. Disrupted sleep, ageing, and neurological conditions can all impair this process.

This project investigated whether **temporal interference (TI) stimulation** can enhance hippocampal-dependent memory consolidation during sleep. TI is a non-invasive technique that uses two intersecting high-frequency electrical currents to generate a low-frequency interference envelope at a precise deep brain target — enabling focused stimulation of structures like the hippocampus that conventional non-invasive methods cannot reliably reach.

The core contribution of this work is **personalised computational modelling** of TI-induced electric fields, using subject-specific MRI and DWI data to quantify how precisely and strongly the stimulation reaches the left hippocampus — and whether that field strength predicts memory outcomes.

---

## Clinical and scientific context

Existing non-invasive brain stimulation techniques (tACS, tDCS) lack the spatial precision to reliably target deep structures. Deep brain stimulation (DBS) can reach them but requires surgery. TI, first demonstrated by Grossman et al. (2017), offers a middle path — non-invasive but capable of deep, focal stimulation.

Violante et al. (2023) provided the first human evidence that TI can modulate hippocampal activity. This project builds directly on that work, using the same stimulation paradigm to model inter-individual variability in field delivery and link it to behavioural outcomes.

---

## Methods

### Sleep study design

26 healthy adults (mean age 26, 15M:14F) underwent a 90-minute nap opportunity. Participants completed an associative memory encoding task pre-nap (face-object pairs) and a recognition test post-nap. EEG monitoring confirmed stimulation was delivered during slow-wave sleep.

Stimulation parameters: f₁ = 2000 Hz, f₂ = 2090 Hz, Δf = 90 Hz, current 1:3 mA, 4-second duration. Four scalp electrodes (1.5 cm radius each).

### Computational modelling pipeline

Subject-specific head models were constructed from T1-weighted MRI and DWI data for 26 participants. Simulations were run in **Sim4Life v8.2**:

- Automated tissue segmentation: scalp, skull, CSF, grey matter, white matter, subcortical structures
- Mask-specific segmentation of left and right hippocampi
- Electric field computation across the full head volume
- Median field strength and selectivity calculated per participant to quantify targeting accuracy

### Outcome measures

Recognition accuracy compared pre- and post-nap. Participants split by encoder type (high vs low baseline performers). Electric field model data correlated with individual memory accuracy changes.

---

## Results

### Electric field modelling

The TI montage produced focused stimulation in the left hippocampus, with minimal spread to surrounding cortical areas. Left hippocampal field strength was stronger and more spatially concentrated than right, confirming successful lateralisation of the electrode montage.

### Behavioural outcomes

Splitting by encoder type revealed state-dependent effects:

- Low encoders showed significant memory gains with TI stimulation + delayed retrieval cue
- Memory improvement correlated with hippocampal field strength: **r = 0.64, p = 0.026**
- No significant effects observed in high encoders

This suggests stimulation efficacy depends on baseline hippocampal state — those with lower baseline encoding performance benefit most, consistent with homeostatic plasticity principles.

---

## Key findings

- Personalised TI modelling is feasible using standard MRI/DWI acquisition protocols
- Left hippocampal field strength is predictable from individual anatomy and electrode placement
- There is significant inter-individual variability in field delivery — supporting the need for personalised rather than standard montages
- TI stimulation during SWS selectively enhances memory in low encoders, with effect size scaling with hippocampal field strength
- High encoders show no significant benefit, suggesting a ceiling effect or state-dependency

---

## Repository contents

```
├── README.md
├── final_presentation.pptx        # Project presentation slides
```

> Note: Simulation scripts and analysis code are not included in this repository. Full methodology is documented above and in the presentation.

---

## Tools and technologies

`Sim4Life v8.2` · `SimNIBS` · `MRI (T1-weighted)` · `DWI` · `EEG` · `Python`

---

## Background reading

- Grossman et al. (2017). Noninvasive deep brain stimulation via temporally interfering electric fields. *Cell*
- Violante et al. (2023). Non-invasive temporal interference electrical stimulation of the human hippocampus. *Nature Neuroscience*
- Saturnino et al. (2019). SimNIBS 2.1: A comprehensive pipeline for individualized electric field modelling for transcranial brain stimulation. *NeuroImage*
- Esmaeilpour et al. (2021). Temporal interference stimulation targets deep brain regions by modulating carrier frequency fields. *Brain Stimulation*

---

## Author

**Diya Joseph** — MEng Biomedical Engineering, King's College London
[LinkedIn](https://linkedin.com/in/YOURUSERNAME) · [Email](mailto:YOUREMAIL)

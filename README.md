# Indian Pedestrian Intention Dataset – Subset (IPID-Subset)

![Dataset Sample Collage](https://i.ibb.co/Q3qmS1jx/dataset-collage.png)

---

## Overview
This repository provides a **subset** of the Indian Pedestrian Intention Dataset (IPID), prepared specifically for reviewer access.  
The subset includes selected video clips and annotations covering representative pedestrian behaviors in unstructured Indian traffic scenarios.

Unlike the full dataset (43 minutes, 240 clips), this subset is small and lightweight, intended for quick download and evaluation.

---

## Dataset Characteristics

- **Total Duration**: 3 minutes 12 seconds  
- **Total Size**: 153 MB  
- **Number of Video Clips**: 17  
- **Clip Lengths**: 6–17 seconds  
- **Resolution**: 1920×1080 (Full HD)  
- **Frame Rate**: 29.97 FPS  
- **Annotation Format**: XML (CVAT compatible)

---

## Repository Structure
```
ipid-subset/
├── clips/
│ ├── clip_002.mp4
│ ├── clip_010.mp4
│ └── ...
├── annotations/
│ ├── clip_002.xml
│ ├── clip_010.xml
│ └── ...
└── README.md
```

---


## Usage

Annotations are in **CVAT-compatible XML** format.  
Example loading code:

```python
import cv2
import xml.etree.ElementTree as ET

# Load video
cap = cv2.VideoCapture('clips/clip_002.mp4')

# Parse annotations
tree = ET.parse('annotations/clip_002.xml')
root = tree.getroot()

# Process frames with annotations
for frame_id in range(int(cap.get(cv2.CAP_PROP_FRAME_COUNT))):
    ret, frame = cap.read()
    if not ret:
        break
    # Use parsed annotations here
```

## License
This subset is released under the MIT License. See LICENSE for details.

## Contact
For questions or collaboration:
Email: 
Issues: GitHub Issues

## Acknowledgment
This subset is derived from the full Indian Pedestrian Intention Dataset (IPID), collected in Trivandrum, Kerala, India.

# Telebort Public Datasets

Public datasets for Telebort AI and Machine Learning courses. These files are hosted here to enable automatic data loading in Google Colab and Jupyter notebooks.

## Courses

### AI-1: Data Analysis and Data Science
| File | Size | Description |
|------|------|-------------|
| `AI-1/googleplaystore.csv` | 1.3 MB | Google Play Store apps dataset for project-04 |

### AI-2: AI, Machine Learning & Computer Vision

**CSV/JSON Data:**
| File | Size | Description |
|------|------|-------------|
| `AI-2/csv/vgsales.csv` | 1.3 MB | Video game sales dataset for activity-05 |
| `AI-2/csv/socr_height_weights.csv` | 4.8 KB | Height/weight data for activity-06 regression |
| `AI-2/csv/Live.csv` | 358 KB | Facebook Live data for activity-08 clustering |
| `AI-2/csv/Instagram.csv` | 47 KB | Instagram reach data for project-01 |
| `AI-2/csv/titanic_train.csv` | 60 KB | Titanic training data for project-02 |
| `AI-2/csv/titanic_test.csv` | 28 KB | Titanic test data for project-02 |
| `AI-2/csv/Mall_Customers.csv` | 3.9 KB | Mall customer data for project-03 |
| `AI-2/csv/intents.json` | 5.7 KB | Chatbot intents for project-04 |

**Image/Video Files:**
| File | Size | Description |
|------|------|-------------|
| `AI-2/images/outing.jpg` | 76 KB | Sample image for activity-13 OpenCV |
| `AI-2/images/outing_large.jpg` | 2.5 MB | Large sample image for activity-13 |
| `AI-2/images/video.mp4` | 981 KB | Sample video for activity-13 |
| `AI-2/images/cats.jpg` | 69 KB | Cat image for activity-14 image processing |
| `AI-2/images/stevejob.png` | 215 KB | Portrait for activity-15 drawing |

## Usage in Notebooks

These files are accessed via raw GitHub URLs. The notebooks use this pattern:

```python
import os
import pandas as pd

DATA_FILE = './data/filename.csv'
DATA_URL = 'https://raw.githubusercontent.com/KCW89/telebort-public-datasets/main/AI-1/googleplaystore.csv'

if os.path.exists(DATA_FILE):
    print("📊 Loading from local file...")
    df = pd.read_csv(DATA_FILE)
else:
    print("📥 Downloading from GitHub...")
    df = pd.read_csv(DATA_URL)

print(f"✅ Dataset loaded! Shape: {df.shape}")
```

## License

These datasets are for educational use in Telebort courses only. Original datasets retain their original licenses.

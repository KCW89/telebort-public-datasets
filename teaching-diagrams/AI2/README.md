# AI2 Teaching Diagrams

Comprehensive visual reference guides for AI2 Machine Learning projects.

## Available Diagrams

### Project 02: Titanic Classification
**File**: `project-02-titanic-classification.excalidraw`

A complete reference guide covering:
- 📊 **File Map**: Jupyter notebook cell structure (Setup → Explore → Clean → Train → Evaluate)
- 🔄 **Data Flow**: ML pipeline stages (Raw CSV → Cleaned → Encoded → Scaled → Trained Model)
- 🤖 **Model Architecture**: Classification pipeline (6 features → KNN/Tree/NB → Binary output)
- ⏰ **Training Timeline**: When each phase happens (Load → EDA → Clean → Encode → Scale → Split → Train)
- ❌ **Common Errors**: Shape mismatches, NaN values, encoding issues
- 🔍 **Debug Checklist**: Systematic troubleshooting (Check shapes, nulls, dtypes, split)
- 🏭 **Sorting Machine Analogy**: Mental model (Dataset = boxes, Features = labels, Model = sorting machine)

**Key Concepts**:
- Binary classification (Survived: 0/1)
- Train/test split (80/20)
- Three models compared: KNN (83%), Decision Tree (78%), Naive Bayes (80%)
- Feature preprocessing: Drop Cabin → Fill Age → Encode Sex/Embarked → Scale to [0,1]
- Shape consistency: Train (712×6) and Test (179×6) must match in features

**Use Cases**:
- Students stuck on "ValueError: could not convert string to float"
- Understanding why order matters in ML pipeline
- Debugging shape mismatch errors
- Comparing multiple classification algorithms
- Visualizing the complete ML workflow

## How to Use

1. **Open in Excalidraw**:
   - Go to [excalidraw.com](https://excalidraw.com)
   - File → Open → Select `.excalidraw` file
   - Or use Excalidraw VS Code extension

2. **Export Options**:
   - PNG: For embedding in slides/docs
   - SVG: For high-quality prints
   - PDF: For student handouts

3. **Teaching Tips**:
   - Print Section 7 (Analogy) as a one-pager for students
   - Use Section 5 (Errors) during debugging sessions
   - Reference Section 6 (Checklist) in project rubrics

## Design Standards

All diagrams follow these conventions:
- **Dark theme** (`#121212` background)
- **Color coding**:
  - Orange (#f08c00): Data/Setup phases
  - Blue (#1971c2): Processing/Cleaning
  - Purple (#9c36b5): Encoding/Transformation
  - Green (#2f9e44): Training/Success
  - Red (#c92a2a): Errors/Warnings
- **7-section structure**: Map → Flow → Architecture → Timeline → Errors → Debug → Analogy
- **Font families**: 1=Sans-serif, 3=Monospace (code)

## Contributing

To add new diagrams:
1. Follow the 7-section template structure
2. Use consistent color scheme
3. Include practical debugging advice
4. Add real code examples from solution notebooks
5. Create mental model analogy for complex concepts

## Maintenance

- Update diagrams when project requirements change
- Add new common errors as students encounter them
- Keep accuracy percentages current with solution notebooks
- Sync with course content updates

---

**Last Updated**: December 2024
**Course**: AI2 Artificial Intelligence, Machine Learning & Computer Vision
**Maintainer**: Telebort Engineering

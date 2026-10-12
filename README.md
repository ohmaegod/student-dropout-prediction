# Student Dropout Prediction

Predicting student dropout and academic success from demographic, academic and socioeconomic attributes — carried from research proposal through to final written paper.

**Sole author.** Mapúa Institute of Technology, DS190 Methods of Research, 2024.

---

## Why this repository exists

Most portfolio projects are a notebook. This one is a complete research cycle: a proposal, a literature review across eight peer-reviewed studies, a methodology report, the implementation, and a final paper. It is here because the process is the point — the modelling is deliberately conventional, and what the work demonstrates is the ability to scope a question, ground it in existing research, justify a method, and write up findings to a standard someone else could replicate.

---

## The problem

Student dropout is expensive for institutions and far more expensive for students. The useful version of the question is not *who dropped out* — that is known too late to act on — but *which students are at risk early enough for intervention to matter*. That reframing makes it a classification problem on an imbalanced target, where the cost of a missed at-risk student is much higher than the cost of an unnecessary check-in.

---

## Data

[UCI Machine Learning Repository — Predict Students' Dropout and Academic Success](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)

Public dataset covering enrolment records with demographic, socioeconomic and academic-performance attributes, and a three-class outcome (dropout, enrolled, graduate).

---

## Approach

1. **Literature review** — eight peer-reviewed studies on dropout prediction and early academic-risk identification, establishing which feature families prior work found predictive and where results disagreed.
2. **Preprocessing** — missing-value handling, encoding of categorical attributes, and scaling so no feature dominated by magnitude alone.
3. **Feature engineering** — across three families: demographic, academic performance, and socioeconomic.
4. **Model comparison** — candidate classifiers evaluated on held-out data.
5. **Selection and serialisation** — the chosen model persisted for reuse.

---

## Results

Full model comparison and selected-model metrics are documented in the final paper under `paper/`.

### Limitations

The outcome classes are imbalanced, so headline accuracy flatters any model that leans toward the majority class — per-class recall is the honest read. The dataset covers a single institution, so the factors that matter here may not transfer directly elsewhere. The literature review establishes which feature families prior work found predictive, but this study does not attempt causal inference — everything reported is association, not cause.

---

## Repository layout

```
notebooks/
  student-dropout-and-academic-sucess-data-analysis.ipynb   # EDA
  prediction-of-students-performance.ipynb                  # modelling
models/
  student_dropout_model.pkl
paper/
  final-paper.pdf
requirements.txt
README.md
```

---

## Running it

```bash
pip install -r requirements.txt
# download the dataset from the UCI link above into data/
jupyter notebook notebooks/
```

---

## Stack

Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn · Jupyter

---

## Author

**Aruen Mae Molina** — BS Data Science, Mapúa Institute of Technology
github.com/ohmaegod

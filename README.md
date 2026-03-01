# Learning TensorFlow - Journey to EDISS 2028

My personal learning repository documenting my 2-year journey building skills in TensorFlow, Deep Learning, and Data-Intensive Systems.

## Goal
Prepare for **EDISS (Erasmus Mundus in Data-Intensive and Intelligent Software Systems)** application in 2028.

## Progress Tracker

### Week 1 - Foundations

**Day 1** (January 25, 2025)
- ✅ NumPy fundamentals
- ✅ Array operations, slicing, indexing
- ✅ Boolean indexing and broadcasting
- ✅ Reshape operations
- File: `day1_numpy_fundamentals.ipynb`

**Day 2** (January 26, 2025)
- ✅ TensorFlow tensor fundamentals
- ✅ Tensor operations and computational graphs
- ✅ Built first neural network (Keras Sequential API)
- ✅ Trained MNIST digit classifier
- **Result: 90% test accuracy**
- Files: `day2_tensorflow_fundamentals.ipynb`, `day2_mnist_classifier.ipynb`

**Day 3** (January 27, 2025)
- 🏥 Rest day - health first
- 📝 Organized repository and documentation

---

## What I'm Learning

### Core Skills
- TensorFlow & Keras
- Neural Network Architecture
- Data Preprocessing
- Model Training & Evaluation

### Next Steps
- Improve MNIST accuracy to 97%+
- Build more complex architectures
- Work with real-world datasets


**Day 3** (January 29, 2026)
- ✅ Normalization experiments (255, 256, 128)
- ✅ Improved model with Dropout layers
- ✅ Training visualization (accuracy + loss curves)
- ✅ Error analysis and confusion matrix
- ✅ Confidence analysis on wrong predictions
- **Result: 98.11% test accuracy**
- File: `day3_improving_mnist.ipynb`


**Day 4** (February 2, 2026)
- 🔬 **Research Project:** [Pakistani Truck Art Style Classifier](https://github.com/T-ajwer/Truck_art_classifier-)
- 🎯 **Focus:** Experimental study on class imbalance and data scarcity
- 📊 **Dataset:** 139 images, severe imbalance (10-47 per class)
- 🔍 **Key Finding:** Demonstrated why 100% accuracy on 2 samples is statistically meaningless
- 💡 **Lessons:** Minimum dataset requirements, overfitting analysis, critical metric interpretation
- **Status:** Published as standalone research project

**Key Insight:** Real-world ML often involves data constraints. Documenting these challenges honestly demonstrates scientific maturity.



# 🚀 Machine Learning Journey - Tajwer Fatima

**Goal:** Building toward graduate ML programs (EDISS 2028) through daily hands-on learning

**Current Status:** Day 6 of 700-day journey  
**Started:** January 25, 2026

---

## 📊 Projects

### 🎨 Project 1: Pakistani Truck Art Classifier (Day 4)
**Repository:** [Truck_art_classifier](https://github.com/T-ajwer/Truck_art_classifier-)

**Objective:** Research study on class imbalance effects in CNNs

**Dataset:**
- 139 images across 4 style categories
- Severely imbalanced: Floral (35), Geometric (45), Portrait (47), Calligraphy (12)

**Approach:**
- Transfer learning with MobileNetV2
- Data augmentation techniques
- Per-class accuracy analysis

**Results:**
- Overall validation: 61%
- Calligraphy: 100% accuracy (statistical noise - only 2 validation samples!)
- Discovered: Small validation sets produce unreliable metrics

**Key Learning:**
> Even 100% accuracy can be meaningless without sufficient sample size. This project became a case study on statistical significance in ML evaluation.

**Files:** `day4_truck_art_classifier.ipynb`

---

### 🍕 Project 2: Food Classifier - Pipeline Learning (Day 5)
**Notebook:** `day5_food_classifier_synthetic.ipynb`

**Objective:** Master complete ML pipeline using synthetic data (no dataset download issues)

**Dataset:**
- 600 synthetic images (150 per category: pizza, burger, sushi, pasta)
- Balanced distribution
- Random colored images (noise, not real patterns)

**Approach:**
- MobileNetV2 transfer learning
- Data augmentation (rotation, shifts, zoom, flips)
- Dropout regularization

**Results:**
- Validation accuracy: 40-44%
- Training accuracy: 70-80%
- Overfitting gap: 30-36% (severe)

**Discovery - Training Non-Determinism:**
Ran training twice with identical code:
- Run 1: 70% train / 40% val
- Run 2: 80% train / 44% val

**Analysis:**
- Observed overfitting in real-time (validation decreased after epoch 6)
- Wobbling validation loss indicated model confusion
- Proved: Even powerful models can't extract patterns from pure noise

**Key Learning:**
> Data quality matters more than model complexity. This experiment demonstrated that MobileNetV2 (trained on 1.4M real images) barely beat random guessing (25%) on synthetic noise.

---

### 🐾 Project 3: Animal Classifier (Day 6)
**Notebook:** `day6_animal_classifier.ipynb`

**Objective:** Build real classifier with balanced data, applying lessons from Days 4-5

**Dataset:**
- Animals-10 from Kaggle (~7,000 images)
- 4 balanced categories: Sheep (1,820), Cow (1,866), Squirrel (1,862), Elephant (1,446)
- Clean, real-world images

**Approach:**
- MobileNetV2 transfer learning
- Data augmentation
- Dropout regularization
- Balanced class distribution (learned from Day 4!)
- Quality real data (learned from Day 5!)

**Results:**
- **Training accuracy: 95%**
- **Validation accuracy: 94%**
- **Overfitting gap: Only 1%!** (excellent generalization)

**Observations:**
- Validation curves remained stable (confident learning)
- First 5 epochs: Linear improvement (learning big patterns)
- Later epochs: Fine-tuning subtle distinctions
- No wobbling loss (unlike Day 5)

**Key Learning:**
> Real patterns + balanced data = stable, high-performance learning. The 1% overfitting gap demonstrates healthy generalization.

---

## 📈 The Learning Arc

**Progression Across 3 Projects:**

| Project | Data Quality | Balance | Accuracy | Overfitting Gap |
|---------|--------------|---------|----------|-----------------|
| Day 4: Truck Art | Real, limited | ❌ Imbalanced | 61% | High |
| Day 5: Food | Synthetic noise | ✅ Balanced | 44% | 30-36% |
| Day 6: Animals | Real, abundant | ✅ Balanced | 94% | 1% |

**Hypothesis Proved:**
> Balance + Quality Data = Success

---

## 🎓 Techniques Applied

**From AlexNet (2012) Paper:**
- ✅ ReLU activation (via MobileNetV2)
- ✅ Dropout for overfitting prevention
- ✅ Data augmentation (rotation, flips, shifts, zoom)
- ✅ Transfer learning concept

**Modern Architecture:**
- MobileNetV2 (evolved from AlexNet principles)
- Global Average Pooling
- Batch Normalization
- Depthwise Separable Convolutions

---

## 💡 Key Insights

**Day 4 → Day 5 → Day 6 taught me:**

1. **Class imbalance** creates unreliable metrics (Day 4)
2. **Data quality** matters more than model sophistication (Day 5)
3. **Balanced + real data** produces stable, high-accuracy learning (Day 6)
4. **Training curves** tell the story of learning vs memorization
5. **Overfitting gap** is the key metric for generalization

---

## 🛠️ Technical Stack

- **Framework:** TensorFlow/Keras
- **Architecture:** MobileNetV2 (ImageNet pre-trained)
- **Techniques:** Transfer learning, data augmentation, dropout
- **Tools:** Google Colab, Kaggle datasets, GitHub
- **Languages:** Python, NumPy, Matplotlib

---

## 🎯 Next Steps

- **Day 7+:** Continue building diverse classifiers
- **Month 2:** Start reading ML research papers
- **Month 6:** Begin first research paper
- **2028:** Apply to EDISS and top ML graduate programs



## Day 7: Weather Classifier (Feb 26, 2026)

**Project:** 3-class balanced weather classifier

**Dataset Selection Process:**
- Explored 11 weather categories in dataset
- Noticed severe imbalance (1160 vs 377 images)
- Applied Day 4 lesson: selected balanced categories
- Final selection: Hail (591), Snow (621), Sandstorm (692)

**Results:**
- Training: 97%
- Validation: 96%
- **Overfitting gap: 0.72%** (better than Day 6's 1%!)

**Key Achievement:**
Independently identified and corrected class imbalance before training. This demonstrates:
- Critical data analysis skills
- Application of lessons from previous projects
- Research-level decision making

**Progression:**
- Day 6: 95% train, 94% val
- Day 7: 97% train, 96% val
- Improvement: +2% accuracy, better generalization

**Built during Ramadan** - maintaining consistency despite fasting 🌙


## Day 8: Flower Classifier (Feb 27, 2026)

**Project:** 4-class balanced flower classifier

**Categories:** Sunflower (733), Daisy (764), Rose (784), Tulip (984)

**Results:**
- Training: 96%
- Validation: 94%
- Overfitting gap: 2%

**Key Observation:**
Training curves showed significantly more fluctuation compared to Days 6-7. Analysis revealed this is due to flowers having subtle differences (similar petal structures, varying colors) making pattern learning more challenging than weather phenomena or animal shapes.

**Analytical Insight:**
Recognized that curve stability doesn't determine final accuracy - dataset difficulty affects training dynamics. Both smooth and fluctuating curves can achieve excellent results.

**Progression:**
- Day 6 (Animals): 94% val, smooth curves
- Day 7 (Weather): 96% val, smooth curves  
- Day 8 (Flowers): 94% val, fluctuating curves

**Demonstrated:** Ability to analyze and compare training behaviors across projects - researcher-level observation skills.

**Built during Ramadan** - 3 consecutive days of consistency 🌙

---

## 📫 Connect

- **GitHub:** [T-ajwer](https://github.com/T-ajwer)
- **LinkedIn:** [Tajwer Fatima](https://linkedin.com/in/tajwer-fatima-71822130b)

---

**Journey Stats:**
- 📅 Days completed: 6/700
- 🎯 Projects built: 3
- 📚 Research papers read: 1 (AlexNet)
- 💪 Daily commitment: 1-2 hours
- 🔥 Consistency: Learning in public

*Last updated: February 26, 2026*

---

*Updated daily. Consistency over intensity.*
*Days completed: 4/700*
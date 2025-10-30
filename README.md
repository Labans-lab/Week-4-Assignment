**Week 4 Assignment: AI in Software Engineering – “Building Intelligent Software Solutions”**
# 🧠 Week 4 Assignment: AI in Software Engineering
### Theme: Building Intelligent Software Solutions 💻🤖  
**Name:** [Your Name]  
**Course:** AI in Software Engineering  
**Week:** 4  
**Submission Date:** [Insert Date]  

---

## 📘 Overview
This project explores how Artificial Intelligence enhances software engineering through automation, prediction, and intelligent assistance. It includes:
- Theoretical analysis of AI’s role in development  
- Practical implementation using AI tools (Copilot, Selenium, Scikit-learn)  
- Ethical reflection on fairness and bias in AI systems  

---

##  Part 1: Theoretical Analysis (30%)

### **Q1. How AI-Driven Code Generation Tools Reduce Development Time**
AI tools like **GitHub Copilot** and **Tabnine** speed up development by predicting code completions, generating boilerplate, and suggesting entire functions. They learn from millions of public repositories, enabling context-aware suggestions that minimize manual coding effort.

**Limitations:**
- May produce incorrect or insecure code  
- Lacks project-specific knowledge  
- Can reinforce biases from training data  

---

### **Q2. Supervised vs Unsupervised Learning in Automated Bug Detection**

| Aspect | Supervised Learning | Unsupervised Learning |
|--------|--------------------|-----------------------|
| **Data Type** | Labeled (bug vs no-bug) | Unlabeled |
| **Usage** | Classify code changes | Discover unusual code clusters |
| **Example** | Predict bug presence | Detect anomalies |
| **Limitations** | Needs labeled data | Hard to interpret results |

Supervised learning identifies known bugs; unsupervised models detect new or hidden defects.

---

### **Q3. Bias Mitigation in AI Personalization**
Bias mitigation ensures personalized systems remain **fair and inclusive**.  
If models are trained on unbalanced user data, they may exclude certain groups or show favoritism.  
Tools like **IBM AI Fairness 360** and **Fairlearn** help detect and correct such biases, ensuring equitable recommendations and user experiences.

---

### **Case Study: AI in DevOps**
**How AIOps Improves Deployment Efficiency**
AIOps enhances DevOps by combining automation and intelligence to detect issues early and streamline release cycles.

**Examples:**
1. **Predictive Deployment:** Detects failure likelihood before release and automates rollback.  
2. **Anomaly Detection:** Monitors system logs in real time to auto-adjust resources and prevent downtime.  

---

##  Part 2: Practical Implementation (60%)

### **Task 1: AI-Powered Code Completion**

**Tool:** GitHub Copilot  
**Goal:** Compare AI-suggested vs manual implementation of a sorting function.

#### Manual Code
```python
def sort_by_key(data, key):
    return sorted(data, key=lambda x: x[key])
```

## **AI-Suggested (Copilot)**
```
def sort_by_key(data, key):
    if not data:
        return []
    return sorted(data, key=lambda x: x.get(key, ''))
```

**Analysis (200 Words)**

Copilot generated a more fault-tolerant version that handles empty data and missing keys gracefully. The manual code is simpler but assumes all keys exist. While both achieve O(n log n) time complexity, the AI code is safer for production use. The AI tool accelerated my workflow by reducing boilerplate and suggesting syntax instantly, though it required human review for optimization and clarity. Overall, Copilot improves efficiency by focusing developer effort on higher-level logic rather than syntax.

### **Task 2: Automated Testing with AI**

Tool: Selenium IDE / Testim.io
Goal: Automate login testing for valid and invalid inputs.

 **Test Script (Python + Selenium)**
 ```
 from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()
driver.get("https://example.com/login")
```

# Valid credentials
```
driver.find_element(By.ID, "username").send_keys("user1")
driver.find_element(By.ID, "password").send_keys("pass123")
driver.find_element(By.ID, "login").click()
time.sleep(2)
assert "Dashboard" in driver.title
```

# Invalid credentials
```
driver.get("https://example.com/login")
driver.find_element(By.ID, "username").send_keys("wrong")
driver.find_element(By.ID, "password").send_keys("wrong")
driver.find_element(By.ID, "login").click()
time.sleep(2)
assert "Invalid" in driver.page_source

driver.quit()
```
**Screenshot of Results**
<img width="702" height="104" alt="Screenshot 2025-10-30 122939" src="https://github.com/user-attachments/assets/9d89cc0c-b623-4234-b9ce-3f2e9b16f040" />
**Summary (150 Words)**

AI-enhanced test tools like Testim.io automatically detect UI elements even when layouts change, reducing script maintenance. This improves test coverage and stability compared to manual tests. The AI also prioritizes common user paths and predicts high-risk interactions, ensuring broader coverage with fewer scripts. Overall, AI transforms testing from reactive to proactive, identifying potential UI or logic issues before deployment.

**Task 3: Predictive Analytics for Resource Allocation**

**Dataset:** sickitlearn data set import load_breast_cancer
**Goal:** Use Random Forest to predict issue priority.
```
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, f1_score
from sklearn.datasets import load_breast_cancer
```

**Load the breast cancer dataset from scikit-learn**
``
cancer = load_breast_cancer()
X = pd.DataFrame(cancer.data, columns=cancer.feature_names)
y = pd.Series(cancer.target).map({0: 'High', 1: 'Low'}) # Map target to 'High' and 'Low'
``

**No need to drop NaNs as the scikit-learn dataset is clean**
``
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = RandomForestClassifier(random_state=42)
model.fit(X_train, y_train)
y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
print("F1 Score:", f1_score(y_test, y_pred, average='weighted')) 
```
**Output Screenshot**

<img width="422" height="82" alt="Screenshot 2025-10-30 130305" src="https://github.com/user-attachments/assets/8c79c7c2-c65c-4598-9697-f498ab43e910" />

**Part 3: Ethical Reflection (10%)**

The dataset used may contain imbalanced samples that overrepresent certain cases. If the model relies heavily on such data, it could misclassify underrepresented cases. Using fairness libraries like IBM AI Fairness 360 can evaluate disparities in performance metrics (e.g., accuracy per group) and apply bias correction algorithms such as reweighting or adversarial debiasing to ensure equitable predictions. Ethical awareness is essential to prevent harmful automation and maintain trust in AI-driven decisions.



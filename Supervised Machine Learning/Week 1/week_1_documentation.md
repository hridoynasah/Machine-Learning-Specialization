# Introduction to Machine Learning

## What is Machine Learning?

Machine learning is a transformative technology that you likely interact with multiple times a day, often without realizing it. At its core, machine learning is the science of enabling computers to learn and make decisions without being explicitly programmed. This field empowers systems to analyze data, identify patterns, and improve their performance over time, making them integral to many modern applications.

### Everyday Applications of Machine Learning

Machine learning is embedded in many of the tools and services you use daily. Consider the following examples:

- **Web Search**: When you search for something like "how to make a sushi roll" on engines like Google, Bing, or Baidu, machine learning algorithms rank web pages to deliver the most relevant results. These algorithms analyze vast amounts of data to understand what makes a webpage useful, ensuring you get accurate and helpful information quickly.
  
- **Social Media**: On platforms like Instagram or Snapchat, you can upload photos and tag your friends. Machine learning powers facial recognition technology, which identifies and labels individuals in your pictures, making it seamless to share moments with others.

- **Streaming Services**: After watching a movie like *Star Wars* on a streaming platform, you might wonder, "What other movies would I enjoy?" Machine learning algorithms analyze your viewing history and preferences to recommend similar content, enhancing your entertainment experience.

- **Voice Assistants**: Whether you’re dictating a text message ("Hey Andrew, how’s it going?"), requesting a song ("Hey Siri, play a song by Rihanna"), or searching for nearby restaurants ("Okay Google, show me Indian restaurants near me"), voice-to-text and command recognition rely on machine learning to interpret and respond to your voice accurately.

- **Email Filtering**: When you receive an email with a suspicious subject line like "Congratulations! You’ve won a million dollars," your email service likely flags it as spam. Machine learning algorithms detect patterns in email content to distinguish legitimate messages from spam, keeping your inbox clean.

### Machine Learning Beyond Consumer Applications

While machine learning enhances everyday consumer experiences, its impact extends far beyond personal use. It is rapidly transforming industries and addressing global challenges. Here are a few examples:

- **Environmental Sustainability**: Machine learning is helping combat climate change by optimizing renewable energy systems. For instance, algorithms are used to improve the efficiency of wind turbines, maximizing power generation and contributing to a greener future.

- **Healthcare**: In hospitals, machine learning is aiding doctors by improving diagnostic accuracy. By analyzing medical data, such as imaging or patient records, these systems help identify conditions earlier and more reliably, potentially saving lives.

- **Manufacturing**: In industrial settings, machine learning, particularly computer vision, is used to inspect products on assembly lines. For example, at Landing AI, machine learning systems detect defects in manufactured goods, ensuring higher quality and efficiency in production processes.

### Why Study Machine Learning?

Machine learning is not just a theoretical concept—it’s a practical skill with real-world applications. In this course, you will:

- Learn the fundamentals of machine learning and how it works.
- Implement machine learning algorithms in code, gaining hands-on experience.
- Explore how to build systems that can learn from data and make intelligent decisions.

This course builds on the legacy of an earlier version, which inspired millions of learners and even led to the founding of Coursera. Many of those learners went on to develop innovative machine learning systems or pursue successful careers in artificial intelligence (AI). By embarking on this journey, you’re joining a community of innovators shaping the future of technology.

## Getting Started

Welcome to the exciting world of machine learning! Whether you’re here to build cutting-edge AI systems, advance your career, or simply explore a fascinating field, this course will equip you with the knowledge and skills to succeed. Let’s dive in and begin this journey together.



# The Power and Promise of Machine Learning

## Why Machine Learning Matters

Machine learning, a cornerstone of artificial intelligence (AI), has become a pivotal technology driving innovation across industries. In this course, you will not only explore state-of-the-art machine learning algorithms—many of which power the systems used by leading tech companies—but also gain hands-on experience implementing them. Beyond learning the algorithms, you will discover practical tips and techniques to ensure they perform effectively, allowing you to see their impact firsthand.

### The Rise of Machine Learning

Machine learning emerged as a subfield of AI with the goal of creating intelligent machines. While some tasks, like finding the shortest path for GPS navigation, can be explicitly programmed, many complex problems—such as web search, speech recognition, medical diagnosis from X-rays, or building self-driving cars—require systems that can learn from data. Machine learning enables computers to tackle these challenges by learning patterns and making decisions without explicit instructions.

The versatility of machine learning is evident in its applications across diverse domains:

- **Speech Recognition**: Used in voice assistants and transcription services to understand and process human speech.
- **Computer Vision**: Powers applications like Google Maps Street View and defect detection in manufacturing, as seen in projects at Landing AI.
- **Fraud Detection**: Helps secure financial systems by identifying suspicious activities, such as payment fraud.
- **Augmented Reality and Advertising**: Enhances user experiences and optimizes ad targeting, as explored during work at Google Brain and Baidu AI.
- **Emerging Applications**: From optimizing large-scale agriculture to improving healthcare diagnostics and transforming e-commerce, machine learning is reshaping industries.

Today, hundreds of thousands, if not millions, of professionals are applying machine learning to solve real-world problems. As you master these skills, you’ll have the opportunity to explore exciting applications across various sectors, from manufacturing to healthcare, and perhaps even venture into new industries.

### The Economic and Societal Impact

The potential of machine learning extends far beyond its current applications. A McKinsey study estimates that AI and machine learning could generate an additional $13 trillion in economic value annually by 2030. While the software industry has already seen significant benefits, the greatest untapped opportunities lie in sectors like retail, travel, transportation, automotive, and materials manufacturing. This vast potential has created a strong demand for machine learning expertise, making now an ideal time to develop these skills.

### The Quest for Artificial General Intelligence

Looking to the future, many AI researchers, including myself, are inspired by the dream of achieving Artificial General Intelligence (AGI)—machines with intelligence comparable to humans. While AGI remains a distant goal, possibly decades or centuries away, the path forward involves advancing learning algorithms, often drawing inspiration from the human brain. This course will touch on the quest for AGI later, providing insights into how current machine learning techniques contribute to this long-term vision.

### What’s Next?

By mastering machine learning, you’re not only equipping yourself with a highly sought-after skill but also positioning yourself to make a meaningful impact across industries. In the next section, we’ll explore a formal definition of machine learning and introduce the main types of machine learning problems and algorithms. You’ll also become familiar with key terminology and learn when to apply different algorithms to solve specific problems. Let’s continue this journey and dive deeper into the world of machine learning.


# Defining Machine Learning and Its Major Types

## What is Machine Learning?

Machine learning is the field of study that enables computers to learn and make decisions without being explicitly programmed. This definition, attributed to Arthur Samuel in the 1950s, captures the essence of how machines can improve their performance through experience. A notable example is Samuel’s checkers-playing program. Despite Samuel not being a skilled checkers player himself, he created a program that played tens of thousands of games against itself. By analyzing which board positions led to wins or losses, the program learned to identify favorable moves and avoid poor ones. Over time, this self-play allowed the computer to surpass Samuel’s own checkers-playing ability, demonstrating the power of machine learning to acquire expertise through data-driven experience.

The key insight from this example is that the more opportunities a machine learning algorithm has to learn—such as through repeated games or exposure to data—the better it performs. This principle of learning through experience is fundamental to the field and applies across various applications.

## Types of Machine Learning and Their Algorithms

Machine learning encompasses several approaches, each suited to different types of problems. The two primary types are supervised learning and unsupervised learning, with additional methods like recommender systems and reinforcement learning also playing significant roles. Below is an overview of these types, along with a brief explanation and representative algorithms for each:

- **Supervised Learning**: Algorithms learn from labeled data to predict outcomes or classify new data points (e.g., predicting house prices or identifying spam emails).
  - **Linear Regression**: Predicts a continuous output variable based on input features (e.g., estimating house prices from size and location).
  - **Logistic Regression**: Classifies data into discrete categories (e.g., determining if an email is spam or not).
  - **Support Vector Machines (SVM)**: Finds the optimal boundary to separate classes in classification tasks (e.g., classifying images as cats or dogs).
  - **Decision Trees**: Makes decisions by splitting data into branches based on feature values (e.g., predicting customer churn).
  - **Neural Networks**: Models complex patterns using interconnected layers of nodes (e.g., recognizing handwriting).

- **Unsupervised Learning**: Algorithms find patterns or groupings in unlabeled data without predefined outputs (e.g., clustering customers based on purchasing behavior).
  - **K-Means Clustering**: Groups data into k clusters based on similarity (e.g., segmenting customers for marketing).
  - **Principal Component Analysis (PCA)**: Reduces data dimensionality while preserving variance (e.g., simplifying datasets for visualization).
  - **Hierarchical Clustering**: Builds a tree of clusters to reveal data hierarchies (e.g., grouping similar products).
  - **Autoencoders**: Neural networks that learn to compress and reconstruct data (e.g., denoising images).

- **Recommender Systems**: Specialized algorithms suggest items or content based on user preferences and behavior (e.g., recommending movies on streaming platforms).
  - **Collaborative Filtering**: Recommends items based on user-item interactions (e.g., suggesting movies based on user ratings).
  - **Content-Based Filtering**: Recommends items by matching item features to user preferences (e.g., suggesting books based on genres liked).
  - **Matrix Factorization**: Decomposes user-item interaction matrices to predict preferences (e.g., Netflix’s recommendation engine).

- **Reinforcement Learning**: Algorithms learn by interacting with an environment, receiving rewards or penalties to optimize actions (e.g., training a robot to navigate obstacles).
  - **Q-Learning**: Learns an action-value function to choose optimal actions in a given state (e.g., training a game-playing agent).
  - **Deep Q-Networks (DQN)**: Combines Q-learning with neural networks for complex environments (e.g., playing Atari games).
  - **Policy Gradient Methods**: Directly optimizes the policy that maps states to actions (e.g., training a robot to walk).

Among these, supervised learning is the most widely used and has seen rapid advancements, making it a cornerstone of many real-world applications. This course will delve deeply into supervised learning in the first two parts, while the third part will cover unsupervised learning, recommender systems, and reinforcement learning.

## The Importance of Practical Application

Learning machine learning algorithms is like acquiring a set of powerful tools, such as a state-of-the-art hammer or drill. However, having the tools is only part of the equation—knowing how to use them effectively is equally, if not more, important. Just as providing someone with tools doesn’t guarantee they can build a house, understanding machine learning algorithms doesn’t automatically translate to building successful systems. This course emphasizes practical advice for applying these algorithms, drawing on best practices used by top machine learning engineers.

In the real world, even experienced teams can spend months pursuing ineffective approaches. By learning the right techniques, you can avoid common pitfalls and develop valuable, high-performing machine learning systems efficiently. This course aims to equip you with both the tools and the skills to design and implement robust machine learning solutions, positioning you among the rare individuals who can build impactful systems in today’s world.

## What’s Next?

In the upcoming sections, we’ll explore supervised learning and unsupervised learning in greater detail, including their definitions, applications, and when to use each. You’ll also gain a deeper understanding of how to select the appropriate algorithm for specific problems. Let’s move forward and dive into these core concepts of machine learning.



# Supervised Learning and Regression

## Understanding Supervised Learning

Supervised learning, the most economically impactful type of machine learning today, accounts for approximately 99 percent of the value generated by machine learning applications. It involves algorithms that learn to map inputs (denoted as \( x \)) to outputs (denoted as \( y \)), creating input-to-output mappings. The defining feature of supervised learning is the use of labeled data—examples where both the input \( x \) and the correct output \( y \) (the label) are provided. By training on these input-output pairs, the algorithm learns to predict the output \( y \) for new, unseen inputs \( x \), producing reasonably accurate results.

### Examples of Supervised Learning Applications

Supervised learning powers a wide range of real-world applications by learning from labeled examples. The following table outlines key examples:

| Input \( x \)        | Output \( y \)       | Application             |
|--------------------------|------------------------|--------------------------|
| email                   | spam? (0/1)           | spam filtering           |
| audio                   | text transcripts      | speech recognition       |
| English                 | Spanish               | machine translation      |
| ad, user info           | click? (0/1)          | online advertising       |
| image, radar info       | position of other cars | self-driving car         |
| image of phone          | defect? (0/1)         | visual inspection        |

In each case, the algorithm is trained on a dataset containing input-output pairs (\( x, y \)). After training, it can predict the appropriate output \( y \) for new inputs \( x \) it has never encountered.

## Regression: A Key Type of Supervised Learning

To illustrate supervised learning, consider a practical example: predicting housing prices based on house size. Suppose you have a dataset where the input \( x \) is the size of a house in square feet, and the output \( y \) is the price in thousands of dollars. When plotted, the data shows house sizes on the horizontal axis and prices on the vertical axis.

Imagine a friend wants to know the price of their 750-square-foot house. A supervised learning algorithm can help by modeling the relationship between house size and price. For instance:

- **Linear Model**: The algorithm might fit a straight line to the data, predicting a price of approximately $150,000 for the 750-square-foot house.
- **Non-Linear Model**: Alternatively, a more complex model, such as a curve, might better capture the data’s pattern, predicting a price closer to $200,000.

The choice between a straight line, a curve, or a more complex function depends on the data’s characteristics. Later in this course, you’ll learn how to systematically select the most appropriate model for a given dataset, ensuring accurate predictions rather than arbitrarily choosing the model that yields the highest price.

This housing price example can be visualized as a linear regression graph:

```
Price in $1000's
400 |                                     
300 |                                     
200 |         *                       *   
150 |     *               *         *     
100 | *               *         *         
 50 |                                     
  0 |___________________________________
      0    500    1000   1500   2000   2500
           House size in square feet
```

- The graph shows a straight line fitted to data points (marked with *), where house size (x-axis) ranges from 0 to 2500 square feet, and price (y-axis) ranges from 0 to 400 thousand dollars.
- For a 750-square-foot house, the linear model predicts a price around $150,000, indicated by a point on the line.

This housing price example is a specific type of supervised learning called **regression**. In regression, the goal is to predict a continuous numerical output, such as a house price, which can take any value within a range (e.g., $150,000, $183,000, or $70,000). The algorithm learns from a dataset where the correct output (the “right answer” or label \( y \)) is provided for each input \( x \), enabling it to generalize and predict prices for new houses.

## What’s Next?

Supervised learning, particularly regression, is a powerful tool for predicting numerical outcomes. However, supervised learning also includes another major type called classification, which deals with predicting categorical outcomes. In the next section, we’ll explore classification and how it differs from regression, deepening your understanding of supervised learning’s versatility.



# Classification in Supervised Learning

## Understanding Classification

Supervised learning algorithms learn to map inputs (\( x \)) to outputs (\( y \)), as seen with regression in the previous section, where the goal was to predict a number from infinitely many possible values. The second major type of supervised learning is **classification**, which focuses on predicting a category from a small, finite set of possible outputs. Let’s explore this using breast cancer detection as an example.

### Classification Example: Breast Cancer Detection

In breast cancer detection, a machine learning system can assist doctors by diagnosing whether a tumor is **benign** (non-cancerous, labeled as 0) or **malignant** (cancerous, labeled as 1) based on medical records. Early detection is critical, as it can potentially save lives. Suppose your dataset includes tumor sizes (in centimeters) and their corresponding labels:

| Tumor Size (cm) | Diagnosis |
|-----------------|-----------|
| 2               | 0         |
| 5               | 0         |
| 1               | 0         |
| 7               | 1         |
| ...             | ...       |

This data can be visualized on a graph where the horizontal axis represents tumor size (\( x \)), and the vertical axis represents the diagnosis (\( y \)), which takes only two values: 0 (benign) or 1 (malignant). Alternatively, the data can be plotted on a line:

```
Diameter (cm)
0cm        2        5        7       10cm
|----O----O----O----X----O----X----X----|
O = benign, X = malignant
```

If a new patient has a tumor of a certain size (e.g., 3 cm), the classification algorithm predicts whether it is benign (0) or malignant (1). Unlike regression, which predicts from infinitely many numbers, classification deals with a limited set of categories—here, just 0 or 1—making it distinct.

### Classification with Multiple Categories

Classification problems can involve more than two categories. In the breast cancer example, a malignant tumor might be further categorized into different types, such as type 1 or type 2. Using symbols to represent categories:

- \( O \): Benign
- \( X \): Malignant type 1
- \( \triangle \): Malignant type 2

This results in three possible output categories: benign (0), malignant type 1 (1), or malignant type 2 (2). The data can be plotted on a line:

```
Diameter (cm)
0cm        2        5        7       10cm
|----O----O----O----X----O----△----X----|
O = benign, X = malignant type 1, △ = malignant type 2
```

In classification, the terms "classes" and "categories" are used interchangeably to refer to these output labels. Categories don’t have to be numeric; for example, a classification algorithm might predict whether an image depicts a cat or a dog (non-numeric categories). However, when categories are numeric (e.g., 0, 1, 2), they represent discrete classes, not continuous values like 0.5 or 1.7, which distinguishes classification from regression.

### Using Multiple Inputs in Classification

So far, we’ve used a single input—tumor size—to predict the diagnosis. However, classification can incorporate multiple inputs for better predictions. Suppose you also have the patient’s age in addition to tumor size. The dataset might look like this, with circles (\( O \)) for benign tumors and crosses (\( X \)) for malignant tumors:

```
Age
^  malignant
|  X  X  X  X  X
|  X  O  X  X  X
|  O  O  O  X  O
|  O  O  O  O  O  benign
+-----------------> Tumor Size
```

A new patient’s data point (e.g., age and tumor size) can be plotted on this graph. The classification algorithm learns to draw a boundary separating benign and malignant cases, helping the doctor predict the diagnosis. For example, a boundary might look like this:

```
Age
^  malignant
|  X  X  X  X  X
|  X  O  X  X  X  \
|  O  O  O  X  O   \
|  O  O  O  O  O  benign
+-----------------> Tumor Size
```

The boundary (diagonal line) indicates that tumors above it are more likely malignant, while those below are more likely benign. In practice, breast cancer detection systems use many more inputs, such as tumor thickness, uniformity of cell size, and cell shape, to improve prediction accuracy.

## Recap: Supervised Learning Types

Supervised learning maps inputs (\( x \)) to outputs (\( y \)) using labeled data (the “right answers”). It includes two main types:

- **Regression**: Predicts a number from infinitely many possible outputs (e.g., house prices).
- **Classification**: Predicts a category from a small set of possible outputs (e.g., benign or malignant tumors).

The following summarizes the distinction:

| Type          | Prediction Goal               | Example Output          |
|---------------|-------------------------------|-------------------------|
| Regression    | Predict a number (infinite possibilities) | House price: 150,000, 183,000, etc. |
| Classification | Predict a category (finite possibilities) | Tumor diagnosis: 0, 1, 2 |

## What’s Next?

You now understand supervised learning, encompassing both regression and classification. The next major type of machine learning is unsupervised learning, which we’ll explore in the upcoming section.




# Introduction to Unsupervised Learning and Clustering

## What is Unsupervised Learning?

Unsupervised learning is a major type of machine learning, distinct from supervised learning, which we discussed previously. In supervised learning, data includes both inputs (\( x \)) and output labels (\( y \)), such as classifying tumors as benign (\( O \)) or malignant (\( X \)) based on tumor size and patient age. For example:

```
Age
^  malignant
|  X  X  X  X  X
|  X  O  X  X  X  \
|  O  O  O  X  O   \
|  O  O  O  O  O  benign
+-----------------> Tumor Size
```

In contrast, unsupervised learning works with data that has no output labels (\( y \)). Using the same tumor size and patient age dataset, but without labels indicating whether tumors are benign or malignant, the data might look like this:

```
Age
^
|  *  *  *  *  *
|  *  *  *  *  *
|  *  *  *  *  *
|  *  *  *  *  *
+-----------------> Tumor Size
* = data point (no labels)
```

Here, the goal is not to predict a specific outcome but to identify patterns, structures, or interesting insights within the data. This process is called "unsupervised" because the algorithm isn’t given "right answers" to learn from; instead, it must discover meaningful patterns on its own.

## Clustering: A Key Type of Unsupervised Learning

A common type of unsupervised learning is **clustering**, where the algorithm groups data points into clusters based on similarity. In the tumor size and age dataset, a clustering algorithm might identify two distinct groups:

```
Age
^
|  *  *  * | *  *
|  *  *  * | *  *
|  *  *  * | *  *
|  *  *  * | *  *
+-----------------> Tumor Size
Cluster 1    Cluster 2
```

This grouping suggests that the data naturally separates into two clusters, which might represent underlying patterns (e.g., different risk profiles), even without labels.

### Example 1: Clustering in Google News

Clustering is widely used in applications like Google News, which processes hundreds of thousands of news articles daily. The algorithm groups related stories into clusters without being told which topics to focus on. For instance, a cluster might form around articles about a panda birth at a zoo:

| Article Headline                                      | Key Words               |
|-------------------------------------------------------|-------------------------|
| Giant panda gives birth to rare twin cubs at zoo      | panda, twin, zoo        |
| Twin panda cubs born at Japan’s oldest zoo            | panda, twin, zoo        |
| Zoo celebrates birth of twin pandas                   | panda, twin, zoo        |
| Rare twin panda cubs born in Japanese zoo             | panda, twin, zoo        |
| Panda twins arrive at historic zoo in Japan           | panda, twin, zoo        |

The clustering algorithm identifies articles with similar words (e.g., "panda," "twin," "zoo") and groups them together, enabling Google News to present related stories. This process is unsupervised because no one explicitly tells the algorithm to cluster around these words—the algorithm learns the patterns independently.

### Example 2: Clustering DNA Microarray Data

Unsupervised learning is also applied in genetics, particularly with DNA microarray data, which measures gene expression across individuals. Imagine a grid where each column represents a person, each row represents a gene, and colors (red, green, gray) indicate the activity level of a gene for that person:

```
Gene Expression Grid
Genes:  Eye Color  Height  Broccoli Dislike
Person 1: [Red]    [Green]  [Gray]
Person 2: [Green]  [Red]    [Gray]
Person 3: [Red]    [Green]  [Red]
...
```

A clustering algorithm might group individuals into types based on gene expression patterns:

- **Type 1**: Individuals with similar eye color and height genes.
- **Type 2**: Individuals with a genetic dislike for broccoli.
- **Type 3**: Another distinct group based on other gene similarities.

This is unsupervised because the algorithm isn’t told in advance what “types” of people exist—it discovers these groupings by identifying patterns in the data.

### Example 3: Market Segmentation

Companies often use clustering to segment customers based on large datasets of customer information. For example, the DeepLearning.AI team analyzed their community to understand learners’ motivations, identifying distinct groups:

| Cluster         | Primary Motivation               |
|-----------------|----------------------------------|
| Cluster 1       | Seeking knowledge to grow skills |
| Cluster 2       | Developing career (e.g., promotion, new job) |
| Cluster 3       | Staying updated on AI’s impact in their field |

This market segmentation helps tailor services to different customer needs. The algorithm identifies these groups without being given predefined categories, making it an unsupervised learning task.

## Summary and Next Steps

Clustering, a type of unsupervised learning, groups unlabeled data into meaningful clusters, as seen in applications like news aggregation, genetic research, and market segmentation. Unsupervised learning is powerful because it uncovers hidden structures without requiring labeled data. Beyond clustering, there are other types of unsupervised learning algorithms, which we’ll explore in the next section.

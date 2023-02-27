---
title: 'System Thinking in E-commerce ML'
date: 2022-12-01
permalink: 
tags:
  - Machine Learning
  - System Thinking
  - Industrial Production
---

Over the past year, I have been actively advocating for the use of system thinking in the design and development of industrial ML systems. This blog post serves as a documentation of my thought processes.

## Preface

My interest in system thinking was first piqued in 2019 during the height of deep learning's popularity. While I was utilizing deep learning (DL) techniques in production and doing research, I began to question whether DL was the best approach for creating a system that operates on multiple components and complex operation logics. I realized that deep learning, at its core, is simply an algorithmic approach to pattern recognition. It may not necessarily lead to a system that operates efficiently. Moreover, I became increasingly curious about the algorithmic nature of deep learning, its limitations, and why it may or may not work.

## About Deep Learning 

To clarify, I am not opposed to the use of deep learning. In fact, it would be silly to ignore DL's potential in the current year of 2022. However, I do believe that there are two issues with deep learning that cannot be overlooked, and unfortunately, there is no easy solution to either problem.

To illustrate, let's consider how we were taught to perform statistical analysis (or machine learning) in college, using linear regression to predict outcomes. Theoretically, we can justify almost everything about linear regression, including its ability to express models, the effectiveness of finding the global optimum of the empirical risk minimization, the behavior of the solution on unseen data, and other asymptotic and non-asymptotic properties. From an engineering standpoint, we have sufficient guidelines to implement, debug, and iterate the model to ensure the best expected results. However, how many of these same facts can be applied to deep learning?

The mechanisms of deep learning models still hold many unknowns. While some progress has been made in understanding deep learning models, especially from a statistical standpoint, much of what has been discovered so far has been limited to simpler scenarios. For example, we can prove many properties of deep learning models using a two-layer MLP with SGD on i.i.d data. However, deep learning models are generally too complex to study throughtly, with numerous configurations that may each exhibit a different behavior. While academic investigations have shed light on the role of many individual model components, putting them together in the best possible way is not as simple as building with Lego blocks. Deep learning still remains largely a laboratory science, similar to how biomedical lab workers decode protein structures by experimenting with countless configurations one-by-one.

In my expereince, making deep learning work in industry still demands significant resources and efforts. In the past, a couple of data scientists could develop and maintain linear models, which are still in use today by many traditional industries.
Those who are just join industry from school may disagree with my arguments as there are thousands of ML accomplishments published in top-notch conferences every year, some of which are truly groundbreaking. I apologize for being synical, but the academic approach to developing machine learning solutions is inadequate for solving industry problems. Academic approaches are often developed in restrictive environments with the aim of rigorously formulating, justifying, and evaluating the approach. In contrast, industrial approaches must account for the unpredictable and uncontrollable factors in an open environment. In other words, academic workers can situate themselves in a well-defined world, while industrial workers have to deal with the chaotic and unknown nature of the real world. How does this affect people's opinions on problem-solving?



## What do I mean by System Thinking

Based on the aforementioned context, I will elucidate how system thinking can act as a bridge that may resolve the disparities between science and practice. Specifically, system thinking accentuates the interrelatedness of things, which compels us to acknowledge the imprecise and intricate definitions of a seemingly uncomplicated problem. 
The key to system thinking is to understand how everything is connected to everything else. With a holistic view of an open-ended problem, we are more likely to learn and identify the key leverage points (such as particular patterns in the data or advantage of a model) faster, avoid the resistance from the unpredictable and uncontrollable environment, and most importantly, making our decision consistent with the target goal. In fact, system thinking has been widely adopted by other disciplines including physics, biology, and control theory. 

Based on my experience, unexpected side effects, particularly resistance from the environment that obstructs industiral ML system from achieving the intended outcome, typically arise due to a mismatch between the dynamic complexity of the system we construct and our cognitive ability to comprehend that complexity. 
This disparity is not solely due to employing inappropriate technical knowledge and tools to model the problem, but our prior beliefs can also systematically lead us to incorrect assumptions regarding the interactions between the system and the environment, even in seemingly uncomplicated scenarios. Specifically, our prior beliefs often neglect to consider the constantly evolving environment, the interdependence of pipelines and acting components within a production system, the feedback loops governing our decisions and the future environment, how customers self-organize and adapt to our systems, the delays in feedback channels, and the opposing factors that cause ostensibly straightforward solutions to fail.


While an open-end environment is dynamic, evolving, and interconnected, our prior beliefs are often static, shallow, and isolated. 
The underlying cause of this phenomenon is that our heuristics regarding the causal attributions of the system frequently fail to encompass the complexity of the open world (i.e., the limitations of human cognition), and unfortunately, our flawed beliefs are reinforced by our selective interpretation of the facts. Consequently, the first step in adopting system thinking is to the static and isolated views of ML systems, and endeavor to contemplate the dynamics, evolution, and interconnections within the system. In particular, our comprehension of the dynamics and evolution of the system should consider that our decisions will impact the feedback we observe in the future.



## The way I am prcacticing System Thinking

Another cause of unanticipated system side effects lies in our incomplete understanding of the full-range feedback mechanisms operating within an open-ended environment. We are unable to observe how users behave in other contexts, how competing products impact their decision-making processes, and what local events are transpiring, among other things. Although we may attempt to gather as much information as possible, partial information can be as detrimental as no information at all since it can lead to attribution errors and false causal conclusions. In complex systems, cause and effect may be separated distantly in time. Focusing on feedback behaviors and user characteristics may divert attention away from high leverage points, such as enhancing the system by utilizing the structure of the problem. Additionally, feedback delays can impede our ability to test hypotheses and identify real patterns. The oscillation and instability of open-ended environments can be readily discerned by continuously operating the treatment and control systems and analyzing the conclusions drawn from different time intervals. Hence, calibration and sensitivity analysis can be useful in many situations.

What I believe is that no model can replace critical thinking, and that any ML system we choose to build should facilitate the process of system thinking, even if we cannot solve all of the aforementioned problems. As engineers and data scientists, we should use our data-inquiry skills to correct our biases and judgmental errors, rather than reinforcing them. We should also remain aware of confirmation errors, hindsight, defensive thinking, herd mentality, and the fact that all models are wrong, but some are useful. For academic research, system thinking is a valuable tool for bringing models out of the lab. As you can see, system thinking reveals the harsh realities of open-ended environments, and any research that addresses these issues will be practical and problem-driven by nature.


Lastly, one of the most important lessons I have learned is that working with critics is the best way to improve our understanding of open-ended environments. This process can lead to changes in our prior beliefs and conceptions of unpredictable and uncontrollable factors. To conclude, I would like to emphasize a few high-level practices derived from system thinking:
<ol>
<li>The primary goal of developing a system is to solve a problem, not just to gain insights, although insights can be useful for research and exploration. Simple solutions that use basic models or rules should be appreciated if they effectively address the problem. Complex models can provide valuable insights, but using them to solve problems may not yield a good return on investment.</li>
<li>Our model and data analysis should have broad boundaries that account for issues such as limited feedback, erroneous causal attributions, delays, and other unaccounted factors that influence users' decision-making. If a hypothesis or scenario seems restrictive, it probably is. </li>
<li>It's crucial to engage critics, product teams, users, and other stakeholders as partners from the beginning. Their input can help us develop better mental models.</li>
<li>Building a industrial ML system is a continuous, iterative process of testing and redesigning, both for the ML model and our prior beliefs. The environment is dynamic, evolving, and interconnected, and our strategies and mindset should reflect that.
</li>
</ol>
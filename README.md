# AI4SE Final Project

Files:

1. skill_accuracy.ipynb: This notebook presents a comprehensive list of approximately 950 skills gathered from various sources, which were then manually categorized into appropriate ground truth skill groups. The primary goal is to evaluate how effectively a Large Language Model (LLM) can classify these skills into 19 predefined categories using two different prompting strategies. In the first approach, the LLM was asked to classify each of the ~950 skills under the given categories, and its accuracy was assessed by comparing the output to the manually defined ground truth. In the second approach, the LLM was instructed to group the skills into relevant categories directly. Accuracy metrics for both prompting methods were calculated and reported.

2. skill_matching.ipynb: In this notebook, we conducted an analysis using 15 resumes collected from fellow students. First, we asked each student to self-assess their proficiency in a predefined list of 19 skills by rating them on a scale from 0 to 5, which we considered as our ground truth. We then provided the same resumes to a Large Language Model (ChatGPT) and used a prompt to have it rate the same 19 skills on the same scale. Subsequently, we introduced an enhanced prompt with additional guidance on how to rate the skills. Finally, we evaluated the accuracy of the LLM's responses by comparing its ratings from both prompts against the ground truth.

3. GitHub_tasks.ipynb: In this notebook, we selected 10 random closed GitHub issues and manually identified the skills required to resolve each one, establishing a ground truth for evaluation. Using the GitHub API, we gathered comprehensive metadata for each issue, including the title, labels, body, and comments. We then designed two prompting strategies to assess a Large Language Model's (LLM) ability to extract relevant skills. In the first approach, all collected metadata was provided at once, and the LLM was asked to list the necessary skills. In the second approach, each piece of metadata was given separately, and the LLM was prompted to extract skills from each part individually. The accuracy of the model's responses was then evaluated by comparing them to the manually defined ground truth.

4. Final_results.ipynb: In this notebook, we gathered data from users' resumes and their GitHub profiles, including information from pull requests, repositories, and uploaded files. All extracted skill data was organized and stored in a Python dictionary for each user. We then identified open GitHub issues and retrieved their metadata using API calls. With both user and task data in place, we constructed prompts for ChatGPT, asking it to assign the most suitable users to the open tasks based on their skills. Additionally, the LLM was instructed to identify any skill gaps and generate a personalized bootcamp to help users acquire the missing skills necessary to successfully complete the assigned tasks. The model provided justifications for its task assignments and detailed the recommended upskilling plans.



Research Questions:

RQ1) How to collect accurate skill data from users?

To collect user data, we utilize both GitHub IDs and user resumes. In the finalresults.ipynb notebook, the data collection section includes code for extracting information from both sources. We begin by parsing resumes using Python to identify relevant skills. Then, we gather additional data from GitHub, specifically focusing on users' pull requests, repositories, and files uploaded.
To assess the LLM’s performance, we compiled 15 resumes from fellow students, each accompanied by a self-assessment, which serves as our ground truth. The corresponding code and analysis for this evaluation can be found in the skill_matching.ipynb notebook. We tested two different prompt formats to determine how accurately the LLM could extract skills, and we compared the results against the ground truth to measure performance.
Table 1 in the results section of the final paper presents a comparison of skill-matching accuracy achieved by the two different prompting approaches.


RQ2) How to generate a descriptive requirements list to open issues?

We gathered a total of 10 closed GitHub issues from various repositories. Each issue was manually reviewed to identify the necessary skills, which were then used as the ground truth. Using a custom Python script, we interacted with the GitHub API to collect all relevant metadata for these issues. The complete implementation for this process is available in the GitHub_tasks.ipynb notebook.
Table 2 in the final paper presents a comparison of the accuracy of skill extraction from GitHub issues using two different prompting strategies.


RQ3) How to assign open GitHub tasks to the appropriate developer based on relevant skills, and suggest a bootcamp to improve skills when appropriate?

We compiled a list of approximately 950 skills from diverse sources, including Google, ChatGPT, and various technical blogs. Using two different prompts, we instructed a large language model (LLM) to categorize these skills into a set of predefined categories. After the LLM generated its outputs for both prompts, we manually assessed the accuracy of its classifications by comparing them to our original skill list. The implementation for this evaluation is available in the skill_accuracy.ipynb notebook.
Table 3 in the final paper presents a comparison of the categorization accuracy achieved by the two prompt formats.
In the final_results.ipynb notebook, after collecting all relevant user skills and GitHub task data, we provided this information to the LLM through a prompt. The LLM then matched users to tasks based on their skill sets, offered justifications for each assignment, and proposed a tailored bootcamp plan to help users acquire any missing skills necessary to complete their tasks effectively.
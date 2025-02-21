# Requirements

I also have code to start, which does essentially everything (assistant, thread, vector storage, and message creation), but I can't solve the word processing piece with openAI's assistant API. Keeps trying to process as a binary file. I'm not an engineer so I'm sure it'll be easy for the right person.

let me know if you want to see that too. My hope is this is a very quick project. My goal is just to have a python script which can do the work and output a JSON file. No UI required for this one.

if the project goes well, I often have little projects like this (and sometimes larger) that I need help with.

I'm looking for an experienced Python developer with expertise in using the OpenAI API to create a custom AI assistant.

The project involves building a script that creates an AI assistant which processes and answers a list of questions by extracting relevant text from a directory of Word documents (.docx).

Project Requirements:

- use OpenAI Assistant API
- properly create an assistant, threads, and run messages
- properly upload word document files to a vector store which are processed by the assistant
- sequentially ask a list of questions and return relevant information as found in the documents.

Desired Skills:

- proficiency with Python
- familiarity with the OpenAI API (particularly the assistant and file search features).
- troubleshoot file parsing issues and manage binary file uploads.

Deliverables:

- a fully functional Python script that performs the above tasks.
- well-documented code (I can provide you a starting script to accelerate the timeline)

Timeline:

- this should take a couple of hours max for the right person (same day turnaround).

DETAILS
Objective:
Use an open AI assistant to iteratively extract information across a number of word documents in order to answer 20 questions, one question at a time. Then use the responses from the first 20 questions to create a summarized table.
Recommendation: GPT-4. Temperature =< 0.20.

Context: These are HOA documents (for real estate), and the reason we're asking one question at a time is because we found that openAI is much better at extracting one question at a time across many documents, than it is answering all 20 questions at once.

Below is detailed instruction:

1. There would be a list of word documents in a directory.
2. Answers to the 20 questions will exist across the documents and will often exist in multiple documents at once
3. To solve conflicts between documents, there is an authority ranking that's listed below
   4.After the 20 questions are individually answered, create a JSON table, which summarizes the results

Step 1. Use the following “Authority Ranking Order” to determine priority when multiple sources provide overlapping information:

1. CC&R Amendments
2. CC&Rs
3. Bylaws
4. Articles of Incorporation
5. Operating Rules
6. Election Rules
7. Annual Budget Report
8. Financial Statements
9. Reserve Study
10. Reserve Fund
11. Fine Schedule
12. Assessment Enforcement
13. Meeting Minutes
14. Additional Operational Policies & Guidelines
15. Insurance & Evidence of Insurance (COI)
16. Flood & General Liability Insurance

Step 2. Now answer each of the following 20 extraction questions. For each question, use high reasoning effort and, when conflicting information exists, select the details from the highest-ranked source as defined above.

Question 1:
What is the official name of the homeowners association as indicated in the documents? (If multiple sources mention the name, use the information from the highest-ranked document.)

Question 2:
What details are provided about the monthly dues (amounts, payment schedule, and any related conditions)? (Prioritize details from the highest-ranking file available, and note if the dues are aggregate or per property.)

Question 3:
What information is available regarding fee increases and special assessments, including any criteria, frequency, or conditions under which they occur? (Reference the highest-priority document if multiple files address these topics.)

Question 4:
How is the overall financial health of the HOA described, including any metrics, ratings, or commentary on fiscal stability? (Use details from the document highest in the ranking order when available.)

Question 5:
What details are offered about the reserve fund (such as its balance, purpose, and allocation policies)? (If several documents provide this information, select details from the top-ranked source.)

Question 6:
How is the HOA budget allocated among various expense categories, and what insights or breakdowns are provided? (Use the highest-authority source available.)

Question 7:
What does the documentation reveal about the reputation of the management team (including performance, responsiveness, or community feedback)? (Reference the highest-priority document when multiple documents mention management reputation.)

Question 8:
What issues or complaints have been documented, and what information is provided on how they were handled or resolved? (If details come from various sources, follow the ranking order to determine the authoritative source.)

Question 9:
What specific rules and restrictions govern the community, and how are these policies structured or enforced? (Use the highest-ranked document addressing rules and restrictions.)

Question 10:
What policies are in place regarding pets (e.g., permitted types, restrictions, approval processes, or limits)? (If multiple documents include pet policies, prioritize according to the given ranking order.)

Question 11:
What information is provided about short-term rental policies, including any limitations or guidelines? (Refer to the highest-authority document if several files discuss this topic.)

Question 12:
What details are included regarding capital improvements (such as planned projects, recent upgrades, or funding for improvements)? (Prioritize information from the document highest in the provided list.)

Question 13:
How are the community amenities and overall property condition described in the documents? (Use the details from the top-ranked document available on amenities and conditions.)

Question 14:
What information is available on the HOA’s governance practices and transparency, including decision-making processes and access to records? (If multiple documents offer insights, choose the details from the highest-authority file.)

Question 15:
What enforcement measures and fine structures are documented for policy violations, and what are the associated procedures? (When conflicting information exists, refer to the highest-priority source such as Fine Schedule or Assessment Enforcement.)

Question 16:
How does the HOA address routine maintenance and emergency situations, including any protocols or response plans? (Use the highest-ranked document that discusses maintenance and emergencies.)

Question 17:
What processes are outlined for resolving disputes among residents or between residents and management? (If details are provided in several documents, prioritize using the ranking order.)

Question 18:
What details are provided on insurance policies and service coverage, including scope, limitations, and any notable exclusions? (Use the highest-authority document among those addressing insurance, e.g., Insurance & Evidence of Insurance (COI) or Flood & General Liability Insurance.)

Question 19:
What legal or regulatory issues have been identified, and how does the HOA address or mitigate these challenges? (Prioritize details from the highest-ranked document that discusses legal or regulatory matters.)

Question 20:
What evidence or information is provided about resident engagement, involvement, or feedback within the community? (If multiple sources offer information on resident engagement, use the details from the highest-ranked document.)

Please answer each question separately and label your responses (e.g., “Response to Question 1:” etc.).

Step 4. After you have provided the responses to Questions 1–20, please synthesize the information by creating a concise summarization table in JSON format. The table should be an array of objects (rows) where each object contains three keys in the following order:

- "Category" (e.g., HOA Name, Monthly Dues, Fee Increases, Financial Health, Reserve Fund, etc.),
- "Findings" (a summary of the extracted details), and
- "Source" (the name(s) of the document(s) from which the information was drawn).

Ensure that you integrate all the relevant details provided in your earlier responses, and remember to rely on the highest-priority source when there is conflicting information.

Finally, output only the JSON array for the summarization table without any additional commentary.

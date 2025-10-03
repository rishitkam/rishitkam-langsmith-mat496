# rishitkam-langsmith-mat496
Module 1 

Video 1 :
Learnings :
I learnt that through Tracing we can see how the workflow execution is done by LLM and what happened at each step, we can also add some metadata with traces to make it more meaningful, A trace contains runs, including a root run. A very simple way to add traces is using the traceable decorator, traces are a trememdous help in debugging and understanding monitoring performance

Tweaking:
I added custom metadata, including custom metadata at runtime, defined a new function langsmith_rishit which has its own set of input documents instead of using the default function from the repository and traced it, also added metadata in those traces, I have uploaded annotated screenshots in my code to put up a better understanding of whats happening, I added some questions and arguments of my own in the orignal code as well.

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/tracing_basics.ipynb
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module1/tracing_basics.ipynb


Video 2:
Learnings : 
LangSmith gives us the option to specify different run types (like llm, retriever, tools, chain, prompt, parser) in the @traceable decorator. It makes different components of our application render in different ways. Using run types helps categorize and organize traces, making it easier to debug, and understand how different components interact in a workflow

Tweaking : Added my inferences after each sub topic based on the video and the code which i wrote and run, added annotated screenshots of the langsmith interface to further clarify how things are working, defined a new tool of my own "get_stock_price" and used it with run_type = tool, Modified some source codes in LLM run type to give slighly different output format.

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/types_of_runs.ipynb
My code : 

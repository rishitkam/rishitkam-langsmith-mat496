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
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module1/types_of_runs.ipynb


Video 3 :
Learnings : According to our requirements and needs we can apply different tracing methods, apart from the traceable decorator which by default manages our runTree and detects when we make run calls and traces outputs and inputs automatically , Some alternative tracing methods include the Tracing context manager, Wrap_openai, and the Langchain/LangGraph built-in method. The tracing context manager gives us more granular control over what we are tracing, and enables us to log trace for specific blocks of code, giving us more control of what we trace instead of taking care of it automatically like the traceable decorator, the wrap_openai is designed to automatically trace all open_ai calls, Langchain/langGraph built in method traces all the langchain ad langGraph components we use, automatically. We can use the different methods as and when needed, there was also a runTree method which gives us even more granular control over our traces but the video just gave a short one-liner on it and said that we will study it in the future videos.

Tweaking:
defined a completely new RAG function which takes the context from a website (i used wikipedia) and implemented the traceable, tracing context managaer, and wrap open ai tracing methods on it, Then I defined that same function with a new wikipedia source and this time added the LangGraph out of the box tracing method as well and attatched the screenshots from Langsmith showcasing the different tracings, I have also written my own inferences and annotated screenshots in the source code parts and asked some new questions.

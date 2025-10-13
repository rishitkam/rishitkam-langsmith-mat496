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
defined a completely new RAG function which takes the context from a website (i used wikipedia) and implemented the traceable, tracing context managaer, and wrap open ai tracing methods on it, Then I defined that same function with a new wikipedia source and this time added the LangGraph out of the box tracing method as well and attatched the screenshots from Langsmith showcasing the different tracings, I have also written my own inferences and annotated screenshots in the source code parts and asked some new questions along with adding custom metadata at runtime in the different tracing method.

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/alternative_tracing_methods.ipynb
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module1/alternative_tracing_methods.ipynb

Video 4
Learnings : 
conversational threads are a great way to represent a conversation with multiple questions b/w the user and the model, where each question has its own trace, All traces can be tied together using a unique id, this binding together of traces is called a conversational thread, it gives a more chat-bot like interface which we usually see in ai models we talk with, It is basically a series of traces, with each trace representing an invocation in the application, it is a higher level abstraction. we can see the threads in Thread view in LangSmith which provides a pretty neat representation, It is very useful for debugging a full interaction with multiple traces.

Tweakings: Added my Inferences based on the code and the video, defined a new thread id in the metadata and hence created a new conversation thread on the original src code and asked it new questions to test it, defined a systen of my own which is able to have back and forth conversation with a user and stores it all in a thread which gives a very neat final look, almost like an actual ai bot.

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/conversational_threads.ipynb
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module1/conversational_threads.ipynb



Module 2 

Video 1 : 
Learnings : In this video we learned about the importance and value of datasets in measuring the performace of llm applications which by nature are non deterministic and hence testing them is important, datasets are the cornerpeice of our evaluation, whenever we make changes dataset help us to assess if there were improvements due to that change or not. Fundamentally datasets are a list of Examples, you can have both inputs and outputs in an example, You can add tags to dataset to track different versions of it, additionally you can also keep specific examples in a separate split to test on them separately, giving them more importance.

Tweakings: I created new traces and added them to the dataset which we had populated through the source code, I have uploaded screenshots of the tweaks to the dataset which i did through the LangSmith website as most of this video was covering the changes we can make there instead of Jupyter notebook, I added schemas, Tags, splits etc. in the dataset, I created and populated a dataset of my own by writing a code and then applied some other modifications on it through the LangSmith website and Uploaded those screenshots as well. I wrote another new code which populates a dataset with only inputs and no outputs.

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/dataset_upload.ipynb
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module2/dataset_upload.ipynb

Video 2 :
Learnings : This video tells about evaluators, which is the tool we use to ACTUALLY measure perforamce against the examples in datasets, An evaluator runs our application over examples in a dataset and gives metrics like Accuracy or Hallucination, It takes our given input, reference output and the actual output as inputs and calculates metrics, we can define evlaluators using our own code logic or by using llm as judge, furthermore evaluators can be defined in both the jupyter notebook or LangSmith website directly inside the database 

Tweakings : I added my own carefully chosen examples to the existing evaluator in the source code to demonstrate how the score of evaluators changes as the output improves in quality (whatever metric we are using like similarity ot hallucination), I also defined a new evaluator which measured the halucination score of an llm model response based on a reference response using LLM as judge, on a scale of 1-5, 5 being the worst and 1 being the best, Then I tested this evaluator with multiple output types and established its working, then finally I added screenshots to show the Evaluator made by me on the LangSmith website using LLM as judge which I made by following the tutorial video.

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/evaluators.ipynb
My Code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module2/evaluators.ipynb

Video 3 :
Learnings : Experiments is what brings together Datasets and evaluators, It is a process where we run a application over a dataset and evaluate the performance with evaluator, We run the application against each example in a dataset and it creates a new output for each run, the evaluator evaluates each output, We can run an evaluator locally using LangChain SDK or we can run it in the UI on LangSmith Website, We can run experiments over the whole data, specific versions (tags) of the dataset, Splits of the dataset or over specific examples as well, We can experiment on different models, We can also set the repititions, concurrency or metadata in the experiments, repitions define how many times each example will be evaluated,Concurrency specifies how many examples will be processed simultaneously, and with metadata we can add useful metadata to our experiments which helps us to filter experiments later on like "model_name". Overall experiments is a very powerful and helpful tool which helps us to evaluate the performance of LLMs.


Tweakings: Ran the experiments given in the source code on my the source and my own custom dataset, changed the number of splits we were running the experiment on from 1 to 2 i.e ran  experiments on one and then on two splits together, created a new combination of examples to be evaluated using their ID from the langsmith protal , added custom metadata of my own to experiments, Defined a new experiment which evaluated 'contains key terms' , 'has proper citation', and 'is not too short' over two datasets, MAT_496_1 and the one given in the source. Added custom metadata on my the experiment defined by me and also ran that experiment on different splits and on a combination of individual examples

Source code: https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/experiments.ipynb
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module2/experiments.ipynb



Video 4 : 
Learnings : The findings of all the experiments that we ran in our jupyter notebook are very neatly displayed in the LangSmith portal in a very organized manner , Charts have been given to us which are a great way to look at the big picture, We  can add filters to look at and monitor specific test cases, From the experiments summary tab we can open a single experiment in large view to better look at its statistics and can even oven example from it whose traces can also be seen by clicking on them, Evaluators themselves are a type of run and have traces which we can see. We can add filters within the experiment to see specific data, We can compare different experiments side by side by either graphs or other metrics, In summary, LangSmith provides us with a very rich library of functions to analyze the experiments and hence we can get to know about our models in great details.

tweakings:  As there were no source code given, I have made a file which contains the screenshots along with annotations of everything that I did on the Langsmith website in the experiments tab to better analyze them, the link of the file is given below : 
My files : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module2/Analyzing_experiment_results.ipynb

Video 5 : 
Learnings : Sometimes evaluating two models separately and then comparing them may not always give a decisive or desired result, to compare two models head to head we use the pairwise Evaluation, It is especially useful when it difficult to store but easier to compare 2 outputs.

Tweakings : Imported my Own dataset which I custom made and defined a pairwise experiment of my own on two prompts, added screenshots to make things more clear

source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/pairwise_experiments.ipynb
my code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module2/pairwise_experiments.ipynb


video 6 : 
Learnings : Certain evaluation metrics—such as precision, recall, and F1 score, require aggregating results across all examples in an experiment and cannot be computed for individual data points. These are known as summary evaluators. Summary evaluators operate on the complete set of runs and examples from an experiment, enabling the calculation of aggregate performance metrics that provide a holistic view of model behavior.

Tweakings : Added annotated screenshots to explain things better, defined a summary evaluator of my own, added screenshots to explain things better

source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/summary_evaluators.ipynb
my code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module2/summary_evaluators.ipynb


Module 3 

Video 1 : 
Learnings : Langsmith provides the playground environment which is used mainly for Prompt engineering, We usually think of prompts as hard coded strings but prompt templates are another way to give a prompt which have templated variables hydrated by the user at run time, it gives the user more flexibility. With playground we can engineer prompts, compare outputs and even run experiments over data on LLM prompts, Playground also allows us to add tools, and even allows us to open and load datasets into it, we can set output Schemas to maintain consistency and ensure the model gives the output in a specfic format. In summary Playground is an amazing tool for prompt engineering, basically a sandbox for llm prompts.

Tweakings : Added screenshots to explain Playground in LangSmith and demonstrated all its major features, Tried new prompt templates on the already existing dataset, Used repititions on it to see if the answer was accurate, Created a database of my own, Ran it with different prompt templates, compared 2 LLM models using the same prompt templates on this dataset and saw the output

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_3/playground_experiments.ipynb
my code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module3/playground_experiments.ipynb


Video 2 : 
Learnings : In Langsmith there is a tab called the prompts hub which acts as a central repository for designing saving and managing prompt templates, after making a prompt we can commit changes to prompts, push new templates from our code to the prompts hub and also pull templates from the prompts hub to our code, we can even pull specific versions of the code. A prompt template contains changeable variables which are hydrated by the user at the run time, it also includes the model configuration and we can also define an output schema to ensure that our output follows a certain format. (some learnings like output schema and prompt templates were same in both the videos).

Tweakings : I added annotated screenschots to properly explain what I saw and learnt on the langSmith portal, I created my own prompt in the prompts hub, pulled multiple versions of it in multiple ways (with and without the llm model)down,  asked them custom questions, pushed a custom prompt from my code to the prompts hub, Asked some my own peculiar questions in the prompt template which was already given in the question, added my annotations in the notebook to mark the changes and explain things even more further 

Source code : https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_3/prompt_hub.ipynb
My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module3/prompt_hub.ipynb

Video 3 :
Learnings : Basically in this video we took our learnings of playground and prompt hub and tied it all togethet using a RAG application, using traces we can iterate on each prompt, we can change it according to our needs, see the output and then improve it again based on the output, we can test the prompt over any database which is a very helpful thing to efficienty check if our prompt is working fine, After our coke is hooked to a prompt and suppose we commit some more changes to the prompt we dont have to change our code again and again, it reflects the latest commit which is very helpful, to summarise basically we saw and learnt from an end-end example using playground and prompt hub to help iterate over a particular prompt within our application. It was basically the application of the previous two videos combined 
Tweakings : 
Source code: https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_3/prompt_engineering_lifecycle.ipynb
My code : 



Video 4 :
Learnings : we can leverage LLMs to help us write better prompts according to our specific requirements using prompt canvas, which is a tool found in the LangSmith playground interface, we can open it using the magic wand tool, We can ask it to write a completely new prompt, make our existing prompt better , change specific parts of our prompt, standardise prompts, by setting the reading level and the length, etc. these latter parts whcih help us to standardise prompts comes under the category of Quick actions tools which ultimately comes under the prompt canvas itself, there's also a custom action button which lets us make our own quick action tools. It is a very helpful tool especially for standardization of prompts which is a great help in collaboration over organizations .

Tweakings : Since there was no source file for this video, I have made my own jupyter notebook which contains annotated screenshots explaining everything that we did on the langsmith wesbite, and added my own prompt examples, which i made using the prompt canvas features.



My code : https://github.com/rishitkam/rishitkam-langsmith-mat496/blob/main/Module3/prompt_canvas.ipynb




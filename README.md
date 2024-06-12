# meeting_reporter

Code, samples, and a working streamlit app for demonstrating:

1. Multi-agent and human collaboration
2. the use of langgraph to coordinate the interaction
3. the mating of the langgraph and streamlit state machines (non-trivial)

The agents are prompted to create a news story in collaboration with a human(you)from a meeting transcript or minutes which you either provide a URL to or upload. The input agent uploads or downloads the document as appropriate and extracts text from it; the writer agent drafts; the critique agent critiques; you can edit either the draft or the critique. the cycle continues until you are satisfied with a draft at which point it ia given to the output agent to display.

This concept could easily be extended to different types of news stories as well as different sources ands could include fact checking, RAG from an archive etc.

## overview

[langgraph](https://github.com/langchain-ai/langgraph)is a library for building stateful, multi-actor applications with LLMs, built on top of (and intended to be used with) LangChain. It is low-code but not no-code.

The repository is set up so that an application can be uploaded to the Streamlit cloud.

mm_agent.py in this repository contains the main logic and all of the langchain specific code for the application. If you run it as a main program in your own Python environment, it will use tkinter rather than streamlit for UI.

mm_st.py is the main program of the streamlit version and contains all the streamlit specific logic

mytools.py are a few miscellaneous utilities of mine.

mm_tkinter.py contains  the tkinter specific code. It is not used in the streamlit version.

## Ideas for enhancement

1. Select a prompt depending on the content of the source
2. Incorporate fact checking via browsing
3. Include a process for improving the prompts based on frequent critiques
4. Add sources and stories to a database (a morgue in news terms)
5. Use RAG to consult the morgue and get background
6. Embed in a larger collaborative newsroom process
7. Accept audio files for input
8. Incorporate graphics

## privacy

No code here explicitly collects any information of any kind. However, some usage statistics are available from both github and Streamlit

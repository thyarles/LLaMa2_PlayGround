# LangChain Investigation

## Monday, December 18, 2023

Getting back to this ... I think the best resource to follow is the [LLama2 repo](https://github.com/jamesbriggs/llama_2) (wow! Cody sent that to me! I did not type that in!) ... hah! turns out this repo does not exist, and the James Briggs guy is not the same guy from the youtube videos! ... nice try cody!

[Hugging Face Local Pipelines](https://python.langchain.com/docs/integrations/llms/huggingface_pipelines)

## Tuesday, November 21, 2023

Keeping an eye on the running costs of using OpenAI. Yeah it adds up, and I really want to focus on doing everything locally! So no OpenAI or Pinecode stuff at all.

Guessing it will be some variation of LLama2 with Faiss or Chroma or Milva.

To copy files out of the hfpt_Nov20 container, below is a working example of this ...

docker cp 9ef7ecd7959f:/root/.cache/huggingface/hub/models--Salesforce--blip-image-captioning-large  /home/rob/Data3/huggingface/transformers

... notice the "9ef7ecd7959f:/root/.cache ..." 

## Tuesday, November 14, 2023

Got a simple langchain and llama2 page to work! Nice! Llama_2_+_Langchain_Q&A.ipynb

Damn! James Briggs has some real good videos! 

https://www.youtube.com/@jamesbriggs/videos

## Saturday, November 11, 2023

Beginning a dive into langchain. This required I install openai.

pip install openai

I am starting with a youtube video series by Greg Kamradt cuz gotta start somewhere, right?

https://www.youtube.com/playlist?list=PLqZXAkvF1bPNQER9mLmDbntNfSpzdDIU5

This video series references resources from [this](https://github.com/gkamradt/langchain-tutorials) repo.

Another resource to consider will be the youtube channel of James Briggs ...

https://www.youtube.com/@jamesbriggs/videos

Damn! The release cycle for langchain is insane! Almost every day, something new is released!

Hmm had to downgrade the version of openai to ...

pip install openai==0.28.1

... to get it to run, but then immediately ran into rate limits! Sigh ... 

Hmm so yeah, I got to start paying for openai to continue using the api in langchain ... sigh.

Hmm at this point right now, I want to see how to use langchain with either Llama2 or Mistral.

Hmm seems like I need to run stuff with ollama ... 

https://ollama.ai/download

... gonna grab a docker image ...

https://ollama.ai/blog/ollama-is-now-available-as-an-official-docker-image

docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

docker exec -it ollama ollama run llama2

And then to use it with langchain, look [here](https://python.langchain.com/docs/integrations/chat/ollama)

## Friday, January 26, 2024

All of the langchain notebooks ending with "_LMStudio" are using LMStudio to sub in for OpenAI.





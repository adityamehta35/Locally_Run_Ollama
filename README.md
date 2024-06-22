# Running Llama 3 and Phi 3 Mini with Ollama

Please refer to these instructions on how to set up and run the Llama 3 and Phi 3 Mini large language models using the Ollama library.

## Prerequisites

- Docker

- Basic Linux commands

- Installation

## Pull the Ollama Docker Image

Pull the latest Ollama Docker image from Docker Hub:

https://hub.docker.com/r/ollama/ollama

```

docker pull ollama/ollama

```

## Run docker Image with post binding

```

docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

```

## Pull the models

In this case we are going to run llama3 and gemma

```

ollama run llama3

ollama run gemma:7b

```

## Now we can access the models using curl command from the terminal

```

<!-- To access llama3 model -->

curl http://localhost:11434/api/generate -d '{

"model": "llama3",

"prompt":"hi what can you do for me?"

}'



<!-- To access phi3 model -->

curl http://localhost:11434/api/generate -d '{

"model": "gemma:7b",

"prompt":"Hi"

}'

```

## Creating our own Model based on other models:

I have created a Modelfile to act as Eminem, the rapper

Example:

Create a model from llama3

```

ollama create ollama_prompt -f ./Modelfile

ollama run ollama_prompt

**Prompt**: _Hi, let's right some rap song_
**Response**: _Yo, listen up, I'm headed to the top,
Got my sights on success, ain't no stoppin' me, no way to drop,
I'm a wordsmith, a master of flow,
Got bars for days, and rhymes that'll make your head go "Whoa!"

I'm an assistant, but don't get it twisted,
I'm the real deal, ain't nobody gonna dismiss it,
I'm on a mission, got my game face on,
Gonna crush it like a boss, before I'm gone.

So where am I going? Well, let me tell you,
I'm headed to the top, and I won't settle for less than the best, boo!
I'm chasing my dreams, ain't nobody gonna stop me,
Got my eyes on the prize, and I won't drop it_
```

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

ollama run phi3:mini

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

"model": "phi3",

"prompt":"Hi"

}'



```

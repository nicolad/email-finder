# AI SDK, Next.js, and FastAPI Examples

These examples show you how to use the [AI SDK](https://sdk.vercel.ai/docs) with [Next.js](https://nextjs.org) and [FastAPI](https://fastapi.tiangolo.com).

## How to use

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init), [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/), or [pnpm](https://pnpm.io) to bootstrap the example:

```bash
npx create-next-app --example https://github.com/vercel/ai/tree/main/examples/next-fastapi next-fastapi-app
```

```bash
yarn create next-app --example https://github.com/vercel/ai/tree/main/examples/next-fastapi next-fastapi-app
```

```bash
pnpm create next-app --example https://github.com/vercel/ai/tree/main/examples/next-fastapi next-fastapi-app
```

You will also need [Python 3.6+](https://www.python.org/downloads) and [virtualenv](https://virtualenv.pypa.io/en/latest/installation.html) installed to run the FastAPI server.

To run the example locally you need to:

1. Sign up at [OpenAI's Developer Platform](https://platform.openai.com/signup).
2. Go to [OpenAI's dashboard](https://platform.openai.com/account/api-keys) and create an API KEY.
3. Set the required environment variables as shown in [the example env file](./.env.local.example) but in a new file called `.env.local`.
4. `virtualenv venv` to create a python virtual environment.
5. `source venv/bin/activate` to activate the python virtual environment.
6. `pip install -r requirements.txt` to install the required python dependencies.
7. `pnpm install` to install the required dependencies.
8. `pnpm dev` to launch the development server.

## Learn More

To learn more about the AI SDK, Next.js, and FastAPI take a look at the following resources:

- [AI SDK Docs](https://sdk.vercel.ai/docs) - view documentation and reference for the AI SDK.
- [Vercel AI Playground](https://play.vercel.ai) - try different models and choose the best one for your use case.
- [Next.js Docs](https://nextjs.org/docs) - learn about Next.js features and API.
- [FastAPI Docs](https://fastapi.tiangolo.com) - learn about FastAPI features and API.

# email-finder

Below is a brief README-style explanation for running DeepSeek-R1 locally with Ollama.

---

# DeepSeek-R1: Local Setup Guide

This guide explains how to run DeepSeek-R1 on your local machine using [Ollama](https://ollama.ai).

## 1. Install Ollama

1. **Download**: Visit the [Ollama website](https://ollama.ai) and download the installer for your operating system.
2. **Install**: Install Ollama as you would any other application.

## 2. Download and Test DeepSeek-R1

1. **Open Terminal**: Launch your terminal or command prompt.
2. **Run the Model**:

   ```bash
   ollama run deepseek-r1
   ```

   This command automatically downloads the DeepSeek-R1 model (default size) and runs a sample prompt.

3. **Alternate Model Sizes** (optional):
   ```bash
   ollama run deepseek-r1:<size>b
   ```
   Replace `<size>` with `1.5`, `7`, `8`, `14`, `32`, `70`, or `671` to download/run smaller or larger versions.

## 3. Run DeepSeek-R1 as a Service

To keep DeepSeek-R1 running in the background and serve requests via an API:

```bash
ollama serve
```

This exposes DeepSeek-R1 at `http://localhost:11434/api/chat` for integration with other applications.

## 4. Test via CLI and API

- **CLI**: Once DeepSeek-R1 is running, simply type:
  ```bash
  ollama run deepseek-r1
  ```
- **API**: Use `curl` to chat with DeepSeek-R1 via the local server:
  ```bash
  curl http://localhost:11434/api/chat -d '{
    "model": "deepseek-r1",
    "messages": [{ "role": "user", "content": "Hello DeepSeek, how are you?" }],
    "stream": false
  }'
  ```

## 5. Next Steps

- **Python Integration**: Use the `ollama` Python package to integrate DeepSeek-R1 into applications:

  ```python
  import ollama

  response = ollama.chat(
      model="deepseek-r1",
      messages=[{"role": "user", "content": "Hi DeepSeek!"}],
  )
  print(response["message"]["content"])
  ```

- **Gradio App**: Build a simple web interface (e.g., for RAG tasks) using [Gradio](https://gradio.app).

For more details on prompt construction, chunk splitting, or building retrieval-based applications (RAG), refer to the official documentation and tutorials.

---

## References

- [Ollama Documentation](https://ollama.ai)
- [DeepSeek-R1 Article](#) (replace `#` with your desired URL if available)

---

# Ollama DeepSeek-R1 (7b)

This README provides instructions for building and running the Ollama DeepSeek-R1:zb model Docker container and using Lilypad CLI for running on the Lilypad network.

## Prerequisites

- Docker installed on your system
- GPU
- Lilypad CLI installed (for Lilypad network runs)

## Building and Running with Docker

1. Open a terminal and navigate to the directory containing the Dockerfile.

2. Build the Docker image:
   ```
   docker build -t ollama-deepseek-r1-7b
   ```

3. Run the container:

   Basic run with GPU support:
   ```
   docker run --gpus all ollama-deepseek-r1-7b -i Prompt="your prompt here"
   ```

## Running on Lilypad Network

### Using Lilypad LocalNet

To run on the local development network:

```
go run . run --network dev github.com/rhochmayr/ollama-deepseek-r1-7b:0.1.0 --web3-private-key <admin_key> -i Prompt="your prompt here"
```

Replace `<admin_key>` with the admin key found in `hardhat/utils/accounts.ts`.

Example:
```
go run . run --network dev github.com/rhochmayr/ollama-deepseek-r1-7b:0.1.0 --web3-private-key <admin_key> -i Prompt="A lengthy conversation between two physicists about the latest discovery in quantum technology"
```

### Using Lilypad Main Network

To run on the main Lilypad network:

```
lilypad run github.com/rhochmayr/ollama-deepseek-r1-7b:0.1.0 -i Prompt="your prompt here"
```

Example:
```
lilypad run github.com/rhochmayr/ollama-deepseek-r1-7b:0.1.0 -i Prompt="A lengthy conversation between two physicists about the latest discovery in quantum technology"
```

## Notes

- Ensure you have the necessary permissions and resources to run Docker containers with GPU support.
- The module version (`0.1.6`) may be updated. Check for the latest version before running.

## Dependencies and Credits

- [Ollama](https://ollama.com/)
- [DeepSeek-R1](https://ollama.com/library/deepseek-r1)
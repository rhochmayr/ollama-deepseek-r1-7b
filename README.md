# Ollama DeepSeek-R1 (7b)

This README provides instructions for building and running the Ollama DeepSeek-R1:7b model Docker container and using Lilypad CLI for running on the Lilypad network.

## Prerequisites

- Docker installed on your system
- GPU
- Lilypad CLI installed (for Lilypad network runs)

## Building and Running with Docker

1. Open a terminal and navigate to the directory containing the Dockerfile.

2. Build the Docker image:
   ```
   docker build -t ollama-deepseek-r1-7b .
   ```

3. Run the container:

   Basic run with GPU support:
   ```
   docker run --gpus all ollama-deepseek-r1-7b "your prompt here"
   ```

## Running on Lilypad Network

### Using Lilypad LocalNet

To run on the local development network:

```
go run . run --network dev github.com/rhochmayr/ollama-deepseek-r1-7b:1.0.0 --web3-private-key <private-key> -i Prompt="your prompt here"
```

Replace `<admin_key>` with the admin key found in `hardhat/utils/accounts.ts`.

Example:
```
go run . run --network dev github.com/rhochmayr/ollama-deepseek-r1-7b:1.0.0 --web3-private-key <private-key> -i Prompt="There are 49 dogs signed up for a dog show. There are 36 more small dogs than large dogs. How many small dogs have signed up to compete?"
```

### Using Lilypad Main Network

To run on the main Lilypad network:

```
lilypad run github.com/rhochmayr/ollama-deepseek-r1-7b:1.0.0 -i Prompt="your prompt here"
```

Example:
```
lilypad run github.com/rhochmayr/ollama-deepseek-r1-7b:1.0.0 -i Prompt="There are 49 dogs signed up for a dog show. There are 36 more small dogs than large dogs. How many small dogs have signed up to compete?"
```

## Notes

- Ensure you have the necessary permissions and resources to run Docker containers with GPU support.
- The module version (`1.0.0`) may be updated. Check for the latest version before running.

## Dependencies and Credits

- [Ollama](https://ollama.com/)
- [DeepSeek-R1](https://ollama.com/library/deepseek-r1)
# Multi-ModelRoutingSystem
Designed and implemented an adaptive inference routing system that dynamically selects different language models based on prompt complexity to balance inference latency, compute cost, and model capability.

The system evaluates incoming prompts using a custom complexity scoring engine based on:

- reasoning keyword detection
- prompt length
- media/multimodal request indicators

Prompts are then routed to either:

- a lightweight low-latency model for simple requests
- a larger instruction-tuned model for more complex reasoning tasks

The project explored real-world AI infrastructure concepts, including:

- adaptive inference pipelines
- workload-aware model routing
- model selection strategies
- latency vs model-capacity tradeoffs
- GPU memory management
- warm-model vs dynamic-loading architectures

Model Loading Strategy
Colab Implementation
Only the selected model is dynamically loaded during inference to reduce VRAM usage.

Tradeoff:

- lower GPU memory usage
- increased startup latency
- Future Production Extension

In production environments, both models could remain warm as dedicated inference workers to improve routing speed and scalability.

- Technologies Used
- Python
- vLLM
- Hugging Face Transformers
- CUDA GPU Acceleration
- Google Colab
- Future Improvements

Potential future extensions include:

- REST API deployment
- distributed inference workers
- semantic/vector-based routing
- asynchronous request queueing
- AWS/Kubernetes deployment

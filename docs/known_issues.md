<!--
Copyright (c) 2022-2023, NVIDIA CORPORATION. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Known Issues and Limitations

- There is no one-to-one match between our solution and [Triton Inference Server](https://github.com/triton-inference-server/server) features, especially in terms of supporting a user model store.
- Support is currently limited to the x86-64 instruction set architecture.
- Running multiple scripts hosting PyTriton on the same machine or container is not feasible.
- Deadlocks may occur in some models when employing the NCCL communication library and multiple Inference Callables are triggered concurrently. This issue can be observed when deploying multiple instances of the same model or multiple models within a single server script. Additional information about this issue can be found [here](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/usage/communicators.html#using-multiple-nccl-communicators-concurrently).
- Enabling verbose logging may cause a significant performance drop in model inference.
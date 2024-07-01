## Setup Ollama
```bash
(local-rag-example-py3.11) snoopy_kr@iMac local-rag-example % ollama pull mistral
pulling manifest 
pulling ff82381e2bea... 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████▏ 4.1 GB                         
pulling 43070e2d4e53... 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████▏  11 KB                         
pulling c43332387573... 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████▏   67 B                         
pulling ed11eda7790d... 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████▏   30 B                         
pulling 42347cd80dc8... 100% ▕██████████████████████████████████████████████████████████████████████████████████████████████████▏  485 B                         
verifying sha256 digest 
writing manifest 
removing any unused layers 
success 
```

## protobuf 버전 문제
```bash
(local-rag-example-py3.11) snoopy_kr@iMac local-rag-example % poetry add protobuf@3.20  

Updating dependencies
Resolving dependencies... (1.8s)

    Because no versions of fastembed match >0.2.4,<0.2.5 || >0.2.5,<0.2.6 || >0.2.6,<0.2.7 || >0.2.7,<0.3.0
 and fastembed (0.2.4) depends on onnx (>=1.15.0,<2.0.0), fastembed (>=0.2.4,<0.2.5 || >0.2.5,<0.2.6 || >0.2.6,<0.2.7 || >0.2.7,<0.3.0) requires onnx (>=1.15.0,<2.0.0).
    And because fastembed (0.2.5) depends on onnx (>=1.15.0,<2.0.0), fastembed (>=0.2.4,<0.2.6 || >0.2.6,<0.2.7 || >0.2.7,<0.3.0) requires onnx (>=1.15.0,<2.0.0).
(1) So, because fastembed (0.2.6) depends on onnx (>=1.15.0,<2.0.0)
 and fastembed (0.2.7) depends on onnx (>=1.15.0,<2.0.0), fastembed (>=0.2.4,<0.3.0) requires onnx (>=1.15.0,<2.0.0).

    Because no versions of onnx match >1.15.0,<1.16.0 || >1.16.0,<1.16.1 || >1.16.1,<2.0.0
 and onnx (1.15.0) depends on protobuf (>=3.20.2), onnx (>=1.15.0,<1.16.0 || >1.16.0,<1.16.1 || >1.16.1,<2.0.0) requires protobuf (>=3.20.2).
    And because onnx (1.16.0) depends on protobuf (>=3.20.2)
 and onnx (1.16.1) depends on protobuf (>=3.20.2), onnx (>=1.15.0,<2.0.0) requires protobuf (>=3.20.2).
    And because fastembed (>=0.2.4,<0.3.0) requires onnx (>=1.15.0,<2.0.0) (1), fastembed (>=0.2.4,<0.3.0) requires protobuf (>=3.20.2)
    So, because local-rag-example depends on both fastembed (^0.2.4) and protobuf (3.20), version solving failed.

(local-rag-example-py3.11) snoopy_kr@iMac local-rag-example % poetry add protobuf@3.20.2

Updating dependencies
Resolving dependencies... (1.1s)

Package operations: 0 installs, 1 update, 0 removals

  - Downgrading protobuf (5.27.2 -> 3.20.2)

Writing lock file
```

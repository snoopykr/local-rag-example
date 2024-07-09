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

### 에러 메세지
```shell
(local-rag-example-py3.11) snoopy_kr@iMac local-rag-example % streamlit run app.py

  You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8501
  Network URL: http://192.168.0.3:8501

/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/langchain/_api/module_import.py:120: LangChainDeprecationWarning: Importing filter_complex_metadata from langchain.vectorstores is deprecated. Please replace deprecated imports:

>> from langchain.vectorstores import filter_complex_metadata

with new imports of:

>> from langchain_community.vectorstores.utils import filter_complex_metadata

  warn_deprecated(
Fetching 5 files: 100%|███████████████████████████████████████████████████████████████████████████████████████████| 5/5 [00:00<00:00, 14403.52it/s]
2024-07-01 11:21:14.578 Uncaught app exception
Traceback (most recent call last):
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/streamlit/runtime/scriptrunner/script_runner.py", line 567, in _run_script
    self._session_state.on_script_will_rerun(
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/streamlit/runtime/state/safe_session_state.py", line 66, in on_script_will_rerun
    self._state.on_script_will_rerun(latest_widget_states)
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/streamlit/runtime/state/session_state.py", line 514, in on_script_will_rerun
    self._call_callbacks()
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/streamlit/runtime/state/session_state.py", line 527, in _call_callbacks
    self._new_widget_state.call_callback(wid)
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/streamlit/runtime/state/session_state.py", line 271, in call_callback
    callback(*args, **kwargs)
  File "/Users/snoopy_kr/Working/PyCharm/local-rag-example/app.py", line 39, in read_and_save_file
    st.session_state["assistant"].ingest(file_path)
  File "/Users/snoopy_kr/Working/PyCharm/local-rag-example/rag.py", line 36, in ingest
    vector_store = Chroma.from_documents(documents=chunks, embedding=FastEmbedEmbeddings())
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/langchain_community/vectorstores/chroma.py", line 790, in from_documents
    return cls.from_texts(
           ^^^^^^^^^^^^^^^
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/langchain_community/vectorstores/chroma.py", line 726, in from_texts
    chroma_collection = cls(
                        ^^^^
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/langchain_community/vectorstores/chroma.py", line 82, in __init__
    import chromadb
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/chromadb/__init__.py", line 5, in <module>
    from chromadb.auth.token import TokenTransportHeader
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/chromadb/auth/token/__init__.py", line 26, in <module>
    from chromadb.telemetry.opentelemetry import (
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/chromadb/telemetry/opentelemetry/__init__.py", line 11, in <module>
    from opentelemetry.exporter.otlp.proto.grpc.trace_exporter import OTLPSpanExporter
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/opentelemetry/exporter/otlp/proto/grpc/trace_exporter/__init__.py", line 22, in <module>
    from opentelemetry.exporter.otlp.proto.grpc.exporter import (
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/opentelemetry/exporter/otlp/proto/grpc/exporter.py", line 39, in <module>
    from opentelemetry.proto.common.v1.common_pb2 import (
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/opentelemetry/proto/common/v1/common_pb2.py", line 36, in <module>
    _descriptor.FieldDescriptor(
  File "/Users/snoopy_kr/Working/Poetry/virtualenvs/local-rag-example-K3t5StCg-py3.11/lib/python3.11/site-packages/google/protobuf/descriptor.py", line 621, in __new__
    _message.Message._CheckCalledFromGeneratedFile()
TypeError: Descriptors cannot be created directly.
If this call came from a _pb2.py file, your generated code is out of date and must be regenerated with protoc >= 3.19.0.
If you cannot immediately regenerate your protos, some other possible workarounds are:
 1. Downgrade the protobuf package to 3.20.x or lower.
 2. Set PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python (but this will use pure-Python parsing and will be much slower).

More information: https://developers.google.com/protocol-buffers/docs/news/2022-05-06#python-updates
```

### <s>설치 에러</s>
```bash
(local-rag-example-py3.11) snoopy_kr@iMac local-rag-example % poetry add protobuf@3.19.0

Updating dependencies
Resolving dependencies... (4.3s)

Because no versions of streamlit match >1.29.0,<1.30.0 || >1.30.0,<1.31.0 || >1.31.0,<1.31.1 || >1.31.1,<1.32.0 || >1.32.0,<1.32.1 || >1.32.1,<1.32.2 || >1.32.2,<1.33.0 || >1.33.0,<1.34.0 || >1.34.0,<1.35.0 || >1.35.0,<1.36.0 || >1.36.0,<2.0.0
 and streamlit (1.29.0) depends on protobuf (>=3.20,<5), streamlit (>=1.29.0,<1.30.0 || >1.30.0,<1.31.0 || >1.31.0,<1.31.1 || >1.31.1,<1.32.0 || >1.32.0,<1.32.1 || >1.32.1,<1.32.2 || >1.32.2,<1.33.0 || >1.33.0,<1.34.0 || >1.34.0,<1.35.0 || >1.35.0,<1.36.0 || >1.36.0,<2.0.0) requires protobuf (>=3.20,<5).
And because streamlit (1.30.0) depends on protobuf (>=3.20,<5)
 and streamlit (1.31.0) depends on protobuf (>=3.20,<5), streamlit (>=1.29.0,<1.31.1 || >1.31.1,<1.32.0 || >1.32.0,<1.32.1 || >1.32.1,<1.32.2 || >1.32.2,<1.33.0 || >1.33.0,<1.34.0 || >1.34.0,<1.35.0 || >1.35.0,<1.36.0 || >1.36.0,<2.0.0) requires protobuf (>=3.20,<5).
And because streamlit (1.31.1) depends on protobuf (>=3.20,<5)
 and streamlit (1.32.0) depends on protobuf (>=3.20,<5), streamlit (>=1.29.0,<1.32.1 || >1.32.1,<1.32.2 || >1.32.2,<1.33.0 || >1.33.0,<1.34.0 || >1.34.0,<1.35.0 || >1.35.0,<1.36.0 || >1.36.0,<2.0.0) requires protobuf (>=3.20,<5).
And because streamlit (1.32.1) depends on protobuf (>=3.20,<5)
 and streamlit (1.32.2) depends on protobuf (>=3.20,<5), streamlit (>=1.29.0,<1.33.0 || >1.33.0,<1.34.0 || >1.34.0,<1.35.0 || >1.35.0,<1.36.0 || >1.36.0,<2.0.0) requires protobuf (>=3.20,<5).
And because streamlit (1.33.0) depends on protobuf (>=3.20,<5)
 and streamlit (1.34.0) depends on protobuf (>=3.20,<5), streamlit (>=1.29.0,<1.35.0 || >1.35.0,<1.36.0 || >1.36.0,<2.0.0) requires protobuf (>=3.20,<5).
And because streamlit (1.35.0) depends on protobuf (>=3.20,<5)
 and streamlit (1.36.0) depends on protobuf (>=3.20,<6), streamlit (>=1.29.0,<2.0.0) requires protobuf (>=3.20,<6).
So, because local-rag-example depends on both streamlit (^1.29.0) and protobuf (3.19.0), version solving failed.
```

### <s>설치 에러</s>
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
```

### 설치
```bash
(local-rag-example-py3.11) snoopy_kr@iMac local-rag-example % poetry add protobuf@3.20.2

Updating dependencies
Resolving dependencies... (1.1s)

Package operations: 0 installs, 1 update, 0 removals

  - Downgrading protobuf (5.27.2 -> 3.20.2)

Writing lock file
```

### 실행
```bash
streamlit run app.py
```

### Multi PDF 로딩

[참조] https://diptimanrc.medium.com/rapid-q-a-on-multiple-pdfs-using-langchain-and-chromadb-as-local-disk-vector-store-60678328c0df

```python
def load_chunk_persist_pdf() -> Chroma:
    pdf_folder_path = "D:\\diptiman\\dataset\\consent_forms_cleaned"
    documents = []
    for file in os.listdir(pdf_folder_path):
        if file.endswith('.pdf'):
            pdf_path = os.path.join(pdf_folder_path, file)
            loader = PyPDFLoader(pdf_path)
            documents.extend(loader.load())
    text_splitter = CharacterTextSplitter(chunk_size=1000, chunk_overlap=10)
    chunked_documents = text_splitter.split_documents(documents)
    client = chromadb.Client()
    if client.list_collections():
        consent_collection = client.create_collection("consent_collection")
    else:
        print("Collection already exists")
    vectordb = Chroma.from_documents(
        documents=chunked_documents,
        embedding=OpenAIEmbeddings(),
        persist_directory="D:\\testing_space\\chroma_store\\"
    )
    vectordb.persist()
    return vectordb
```

[참조] https://stackoverflow.com/questions/76886954/multiple-file-loading-and-embeddings-with-openai

```python
print("Loading data...")
pdf_folder_path = "content/"
print(os.listdir(pdf_folder_path))

# Load multiple files
loaders = [UnstructuredPDFLoader(os.path.join(pdf_folder_path, fn)) for fn in os.listdir(pdf_folder_path)]

print(loaders)

all_documents = []

for loader in loaders:
    print("Loading raw document..." + loader.file_path)
    raw_documents = loader.load()

    print("Splitting text...")
    text_splitter = CharacterTextSplitter(
        separator="\n\n",
        chunk_size=800,
        chunk_overlap=100,
        length_function=len,
    )
    documents = text_splitter.split_documents(raw_documents)
    all_documents.extend(documents)

print("Creating vectorstore...")
embeddings = OpenAIEmbeddings()
vectorstore = FAISS.from_documents(all_documents, embeddings)

with open("vectorstore.pkl", "wb") as f:
    pickle.dump(vectorstore, f)
```
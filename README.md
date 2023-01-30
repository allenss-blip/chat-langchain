# ChatLangChain

This repo is an implementation of a chatbot specifically focused on question answering over the [LangChain documentation](https://langchain.readthedocs.io/en/latest/).

## 🚀 Important Links

Website: [chat.langchain.dev](https://chat.langchain.dev)

Hugging Face Spage: [huggingface.co/spaces/hwchase17/chat-langchain](https://huggingface.co/spaces/hwchase17/chat-langchain)

Blog Post: [blog.langchain.dev/langchain-chat/](https://blog.langchain.dev/langchain-chat/)

## 📚 Technical description

There are two components: ingestion and question-answering.

Ingestion has the following steps:

1. Pull html from documentation site
2. Parse html with BeautifulSoup
3. Split documents with LangChain's [TextSplitter](https://langchain.readthedocs.io/en/latest/modules/utils/combine_docs_examples/textsplitter.html)
4. Create a vectorstore of embeddings, using LangChain's [vectorstore wrapper](https://langchain.readthedocs.io/en/latest/modules/utils/combine_docs_examples/vectorstores.html) (with OpenAI's embeddings and Weaviate's vectorstore)

Question-Answering has the following steps:

1. Given the chat history and new user input, determine what a standalone question would be (using GPT-3)
2. Given that standalone question, look up relevant documents from the vectorstore
3. Pass the standalone question and relevant documents to GPT-3 to generate a final answer

## 🧠 How to Extend to your documentation

Coming soon.
<script type="text/javascript">
function doZoom(size)
{document.getElementById('zoom').style.fontSize=size+'px';}
</script>
<span id="zoom">需要指定大小的文字</span>
<a href="javascript:doZoom(16)">大</a> <a href="javascript:doZoom(14)">中</a> <a
href="javascript:doZoom(12)">小</a>

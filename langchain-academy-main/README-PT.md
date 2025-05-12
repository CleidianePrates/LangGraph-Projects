Aqui está a tradução para o português:

![LangChain Academy](https://cdn.prod.website-files.com/65b8cd72835ceeacd4449a53/66e9eba1020525eea7873f96_LCA-big-green%20(2).svg)

## Introdução

Bem-vindo à LangChain Academy!
Este é um conjunto crescente de módulos focados em conceitos fundamentais dentro do ecossistema LangChain.
O Módulo 0 é a configuração básica e os Módulos 1 - 4 focam no LangGraph, adicionando progressivamente temas mais avançados.
Em cada pasta de módulo, você verá um conjunto de notebooks. Uma LangChain Academy acompanha cada notebook
para guiá-lo pelo tema. Cada módulo também tem um subdiretório `studio`, com um conjunto de gráficos relevantes
que exploraremos usando a API LangGraph e o Studio.

## Configuração

### Versão do Python

Para aproveitar ao máximo este curso, certifique-se de estar usando Python 3.11 ou posterior.
Esta versão é necessária para compatibilidade ideal com o LangGraph. Se você estiver em uma versão mais antiga,
a atualização garantirá que tudo funcione sem problemas.
```
python3 --version
```

### Clonar repositório
```
git clone https://github.com/langchain-ai/langchain-academy.git
$ cd langchain-academy
```

### Criar um ambiente e instalar dependências
#### Mac/Linux/WSL
```
$ python3 -m venv lc-academy-env
$ source lc-academy-env/bin/activate
$ pip install -r requirements.txt
```
#### Windows Powershell
```
PS> python3 -m venv lc-academy-env
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
PS> lc-academy-env\scripts\activate
PS> pip install -r requirements.txt
```

### Executando notebooks
Se você não tem o Jupyter configurado, siga as instruções de instalação [aqui](https://jupyter.org/install).
```
$ jupyter notebook
```

### Configurando variáveis de ambiente
Breve explicação sobre como configurar variáveis de ambiente. Você também pode
usar um arquivo `.env` com a biblioteca `python-dotenv`.
#### Mac/Linux/WSL
```
$ export API_ENV_VAR="sua-chave-api-aqui"
```
#### Windows Powershell
```
PS> $env:API_ENV_VAR = "sua-chave-api-aqui"
```

### Definir chave API OpenAI
* Se você não tem uma chave API OpenAI, pode se inscrever [aqui](https://openai.com/index/openai-api/).
* Defina `OPENAI_API_KEY` no seu ambiente

### Inscreva-se e Configure a API LangSmith
* Inscreva-se no LangSmith [aqui](https://smith.langchain.com/), saiba mais sobre o LangSmith
* e como usá-lo em seu fluxo de trabalho [aqui](https://www.langchain.com/langsmith), e documentação relevante da biblioteca [aqui](https://docs.smith.langchain.com/)!
* Defina `LANGCHAIN_API_KEY`, `LANGCHAIN_TRACING_V2=true` no seu ambiente

### Configure a API Tavily para busca na web

* A API de Busca Tavily é um mecanismo de busca otimizado para LLMs e RAG, visando resultados de busca eficientes,
rápidos e persistentes.
* Você pode se inscrever para obter uma chave API [aqui](https://tavily.com/).
É fácil se inscrever e oferece um nível gratuito muito generoso. Algumas lições (no Módulo 4) usarão o Tavily.

* Defina `TAVILY_API_KEY` no seu ambiente.

### Configure o LangGraph Studio

* O LangGraph Studio é um IDE personalizado para visualizar e testar agentes.
* O Studio pode ser executado localmente e aberto em seu navegador no Mac, Windows e Linux.
* Veja a documentação [aqui](https://langchain-ai.github.io/langgraph/concepts/langgraph_studio/#local-development-server) sobre o servidor de desenvolvimento local do Studio e [aqui](https://langchain-ai.github.io/langgraph/how-tos/local-studio/#run-the-development-server).
* Os gráficos para o LangGraph Studio estão nas pastas `module-x/studio/`.
* Para iniciar o servidor de desenvolvimento local, execute o seguinte comando no seu terminal no diretório `/studio` de cada módulo:

```
langgraph dev
```

Você deverá ver a seguinte saída:
```
- 🚀 API: http://127.0.0.1:2024
- 🎨 Studio UI: https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
- 📚 API Docs: http://127.0.0.1:2024/docs
```

Abra seu navegador e navegue até a UI do Studio: `https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024`.

* Para usar o Studio, você precisará criar um arquivo .env com as chaves API relevantes
* Execute isto na linha de comando para criar esses arquivos para os módulos 1 a 6, como exemplo:
```
for i in {1..6}; do
  cp module-$i/studio/.env.example module-$i/studio/.env
  echo "OPENAI_API_KEY=\"$OPENAI_API_KEY\"" > module-$i/studio/.env
done
echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" >> module-4/studio/.env
```
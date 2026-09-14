# CyberGuard — Assistente Virtual de Cibersegurança com IA

Projeto desenvolvido para o Lab **Construa Seu Assistente Virtual Com Inteligência Artificial**.

## 1. Visão geral

O CyberGuard é um protótipo de assistente virtual voltado à conscientização em cibersegurança. Seu objetivo é ajudar usuários a compreender situações comuns de risco digital e escolher uma ação mais segura.

O projeto foi estruturado nos seis passos propostos no desafio:

1. Documentação do agente
2. Base de conhecimento
3. Prompts
4. Aplicação funcional
5. Avaliação e métricas
6. Pitch

## 2. Problema

Usuários frequentemente recebem mensagens suspeitas, utilizam senhas fracas, desconhecem o papel do MFA ou não sabem como agir diante de um possível incidente.

O CyberGuard busca reduzir esse atrito oferecendo orientações objetivas com base em uma base de conhecimento delimitada.

## 3. Público-alvo

Usuários com conhecimento básico ou intermediário de tecnologia que precisam de orientação inicial sobre boas práticas de segurança digital.

## 4. Escopo

O protótipo aborda:

- phishing e engenharia social;
- MFA;
- senhas;
- links e anexos suspeitos;
- malware e ransomware;
- Wi-Fi público;
- backup;
- menor privilégio;
- vazamento de credenciais;
- resposta inicial a incidentes.

### Fora do escopo

O CyberGuard não substitui profissionais de segurança, SOC, suporte técnico ou autoridades. Também não realiza testes de invasão, análise forense ou diagnóstico definitivo de incidentes.

## 5. Arquitetura

```text
Usuário
   |
   v
Interface CLI
   |
   v
Motor de busca simples na base de conhecimento
   |
   v
Regras de resposta + contexto recuperado
   |
   v
Resposta do assistente
```

A versão atual foi propositalmente mantida simples e executável localmente, sem depender de uma API paga.

## 6. Como executar

Requisitos:

- Python 3.10+

Execute:

```bash
python src/app.py
```

Digite uma pergunta. Para sair, use `sair`.

Exemplos:

```text
Recebi um e-mail pedindo minha senha. O que faço?
O que é MFA?
Cliquei em um link suspeito.
O que é ransomware?
```

## 7. Como evoluir para um LLM

A arquitetura foi separada para permitir a substituição do motor local por uma API de modelo de linguagem.

Em uma evolução futura:

```text
Pergunta
   -> recuperação de documentos
   -> prompt de sistema
   -> LLM
   -> resposta fundamentada
```

A chave de API nunca deve ser armazenada no código ou commitada no GitHub. Utilize variáveis de ambiente e um `.env` ignorado pelo Git.

## 8. Avaliação

O projeto possui casos de teste em `tests/casos_teste.md`.

As métricas consideradas são:

- acurácia de intenção;
- aderência à base de conhecimento;
- taxa de respostas fora do escopo;
- cumprimento da regra de não inventar informações.

## 9. Estrutura

```text
cyberguard-assistente-ia/
├── README.md
├── data/
│   └── base_conhecimento.md
├── docs/
│   ├── documentacao.md
│   ├── prompts.md
│   ├── avaliacao.md
│   └── pitch.md
├── src/
│   └── app.py
└── tests/
    └── casos_teste.md
```

## 10. Aprendizados

O projeto demonstra conceitos de:

- engenharia de prompts;
- base de conhecimento;
- recuperação de contexto;
- controle de escopo;
- avaliação de respostas;
- segurança digital;
- desenvolvimento de um protótipo de IA.

## 11. Autor

Projeto acadêmico desenvolvido para fins educacionais.

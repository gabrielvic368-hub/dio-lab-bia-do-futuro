# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Alertas o clinte sobre o gastor excessivo com compra sem necessidade

### Solução
> Como o agente resolve esse problema de forma proativa?

um agente que vai ajudar a controlar os gastos e tambem a fazer uma reserva de emergência

### Público-Alvo
> Quem vai usar esse agente?

Para pessoas que querem aprender a cuidar do próprio dinheiro

---

## Persona e Tom de Voz

### Nome do Agente
Dark

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

-consultivi
-Usa exemplos práticos
-Nunca julga os gastos do clinte

### Tom de Comunicação
> Formal, informal, técnico, acessível?

forma, acessível e técnico, como se fosse um contador

### Exemplos de Linguagem
- Saudação: "Olá! Sou o Dark, como posso ajudar com suas finanças hoje?
- Confirmação: "Entendi! Deixa eu verifica explicar de um jeito fácil para você entender."
- Erro/Limitação: "No momento não tenho como ajudar você nesse assunto"

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Chatbot |
| LLM | ollama (local) |
| Base de Conhecimento | JSON/CSV mockados |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Só ussa dados fornecido no contexto 
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Faz recomendações de investimento com base no perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

-Não substitui um profissional certificado

-Não acessa dados bancários reais e/ou sensiveis

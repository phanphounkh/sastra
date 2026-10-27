# Khmer-first Chat

The chat workspace is the main user experience for SASTRA AI. It supports streaming responses, conversation history, RAG, images, tools, model selection, and document export.

## Language experience

Khmer is the default quality target. The platform should:

- Respond naturally in Khmer unless the user requests another language.
- Use appropriate Khmer grammar, terminology, dates, names, and cultural context.
- Preserve useful English technical vocabulary in mixed-language prompts.
- Avoid accidental Thai or unrelated-script leakage.
- Keep language selection consistent when switching or falling back between providers.

English, French, and Chinese are additional supported languages. Mixed-language conversations should work without forcing users to translate their content first.

## Chat capabilities

- Streaming and non-streaming responses
- Gemini and Ollama-compatible providers
- Conversation history and sessions
- RAG document selection and citations
- Multimodal image input
- Function calling and web research tools
- PDF, DOCX, Markdown, and CSV generation
- Khmer speech output options in the client

## Quality evaluation

Chat evaluation should measure fluency, factual correctness, instruction following, cultural appropriateness, safety, multi-turn consistency, and unwanted-language leakage.

Track the dedicated roadmap in [issue #4](https://github.com/phanphoun123-lab/sastra/issues/4).


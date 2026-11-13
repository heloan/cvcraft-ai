# cvcraft-ai

Web panel that tailors your resume to each job posting. You provide your original resume (PDF, DOCX or
plain text), your LinkedIn profile exported as PDF, and the job description and link. Before writing,
the AI asks clarifying questions about the gaps between your resume and the job, and the result follows
resume best practices: single-column ATS-friendly layout, achievements with measurable results, the
job's keywords, and nothing made up. Output in English or Portuguese.

Three AI modes behind the same interface:

- **Copy and paste into claude.ai:** zero cost, uses your Claude subscription; no API key.
- **Gemini (free tier):** automatic, rate-limited. Google may use the submitted content to improve its products.
- **Ollama:** local model, private and free.

Node (Fastify) + React/Vite + TypeScript, running in Docker.

## Status

- In development.

## Structure

```
web/src/<module>/{controller,services,repository,entity}   resume, job, tailoring, ai, export, shared
server/src/<module>/{controller,services,adapters}         llm, job, health
docs/                                                      guides and decisions
scripts/                                                   build and deploy automation
```

## Development

```bash
cp .env.example .env
npm install
npm run dev:server
npm run dev:web
npm test
```

## Privacy

Your resume never leaves your browser unless you choose the Gemini or Ollama mode. Never commit
resumes or exported files to this repository.

## License

MIT

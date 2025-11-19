# Micro-Agent 001: Initial Project Documentation

## 1. Check completion
```bash
[ -f .claude/completed/001 ] && echo "✅ Done $(cat .claude/completed/001)" && exit 0
```

## 2. Task
Create ONE file: `CLAUDE_AGENT_PROMPT.md`

Content:
```markdown
# Citrus Developer Portal - AI Agent Instructions

## Project Overview
Developer portal for Citrus API. Provides documentation, API key management, SDKs, and developer onboarding for integrating with Citrus receipt management platform.

## Technology Stack
- **Framework**: React (check package.json)
- **Language**: TypeScript
- **Styling**: Tailwind CSS / component library
- **Features**: API docs, interactive console, key management
- **Documentation**: MDX / Markdown-based docs

## Project Structure
```
citrus-developer-portal/
├── src/
│   ├── components/     # UI components
│   ├── pages/          # Portal pages
│   ├── docs/           # API documentation
│   ├── api/            # API integration
│   └── App.tsx         # Main application
├── public/             # Static assets
└── package.json        # Dependencies
```

## Development Guidelines

### Code Standards
1. **Developer Experience**: Clear, helpful documentation
2. **Interactive Examples**: Working code samples
3. **API Console**: Test API calls directly
4. **Searchability**: Easy to find information
5. **Accuracy**: Keep docs in sync with API

### Testing Your Changes
```bash
npm run build  # Must pass before completion
npm run dev    # Development server
```

### Branch Strategy
- **Main branch**: `main`
- **Agent branches**: `claude/agent-{NUMBER}-{description}`
- **Pull Requests**: Always create PRs to main

## Common Tasks

### Adding API Documentation
1. Create/update doc pages in `src/docs/`
2. Add code examples
3. Update navigation/search index
4. Test examples in API console
5. Verify accuracy against backend

### API Key Management
1. Generate/revoke keys
2. Scope and permissions
3. Usage analytics
4. Rate limit display

### Developer Onboarding
1. Quick start guides
2. Tutorial series
3. SDK documentation
4. Integration examples

## Important Notes
- This is developer-facing portal (not end-user app)
- Backend: Citrus API
- Keep docs accurate and updated
- Test all code examples
- Related: citrus-admin-dashboard, main Citrus apps

## Available Commands
Check `package.json`:
```bash
npm run dev     # Development server
npm run build   # Production build
npm run docs    # Build documentation (if separate)
```

## Current Priorities
1. Improve API documentation
2. Add interactive examples
3. Enhance developer onboarding
4. Update SDK guides
5. Optimize search and navigation

## Documentation Checklist
- [ ] All endpoints documented
- [ ] Code examples tested
- [ ] Authentication clearly explained
- [ ] Error codes documented
- [ ] Rate limits specified
- [ ] SDKs up to date

---

**Last Updated**: 2025-11-19
**Maintained By**: Micro-Agent 001
```

## 3. Verification
```bash
npm run build
if [ $? -ne 0 ]; then
  echo "❌ Build failed. Review errors and fix code."
  exit 1
fi
```

## 4. Mark Complete
```bash
echo "$(date) - Verified" > .claude/completed/001
```

## 5. Create Pull Request
```bash
git checkout -b claude/agent-001-initial-setup
git add CLAUDE_AGENT_PROMPT.md .claude/completed/001 .claude/agents/001-initial-setup.md
git commit -m "feat: Agent 001 - Initial Project Documentation

- Created CLAUDE_AGENT_PROMPT.md for developer portal
- Emphasized developer experience and documentation
- Verified build successful

🤖 Generated with Claude Code (Verified Build)"
git push -u origin claude/agent-001-initial-setup

gh pr create \
  --title "Agent 001: Initial Project Documentation" \
  --body "## Summary
- Created \`CLAUDE_AGENT_PROMPT.md\` for AI agents
- ✅ Build verification: PASSED
- ✅ Completion marker: \`.claude/completed/001\`

🤖 Generated with Claude Code" \
  --base main
```

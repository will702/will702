# Repo Readiness Checklist

Criteria for determining whether a repository is pin-worthy, ready for showcase, or should be archived.

## Pin-Worthy Criteria

A repository should be pinned if it meets **at least 3 of the following**:

### Code Quality
- [ ] Clean, readable code with consistent style
- [ ] Proper error handling and edge case coverage
- [ ] Modular architecture with clear separation of concerns
- [ ] No hardcoded credentials, API keys, or sensitive data
- [ ] Environment variables or config files for configuration

### Documentation
- [ ] Comprehensive README with overview, setup, and usage
- [ ] Code comments for complex logic and algorithms
- [ ] Architecture diagrams or clear system descriptions
- [ ] API documentation (if applicable)
- [ ] Examples or demo code showing key functionality

### Functionality
- [ ] Working, runnable code (not just proof-of-concept)
- [ ] Clear demonstration of technical capability or shipped output
- [ ] Handles real-world use cases, not just toy examples
- [ ] Performance considerations addressed (if relevant)

### Production Readiness
- [ ] Deployment instructions or scripts
- [ ] Dependency management (requirements.txt, package.json, etc.)
- [ ] Testing (unit tests, integration tests, or manual test procedures)
- [ ] Version control best practices (meaningful commits, branches)

### Impact & Uniqueness
- [ ] Demonstrates unique technical approach or solution
- [ ] Shows measurable results (accuracy, performance, user adoption)
- [ ] Represents significant effort or complexity
- [ ] Has been used in production, hackathons, or research

## Archive Criteria

Archive a repository if it meets **any of the following**:

- [ ] Abandoned or incomplete (no commits in 6+ months, clearly unfinished)
- [ ] Superseded by a newer version or better implementation
- [ ] Contains only learning exercises or tutorial code
- [ ] Broken or non-functional with no clear path to fix
- [ ] Duplicate of another repository
- [ ] Contains sensitive data that cannot be sanitized
- [ ] No longer relevant to current technical focus

## Commit Message Standards

### Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code restructuring without changing functionality
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Maintenance tasks, dependency updates

### Examples
```
feat(ml): Add XGBoost hyperparameter tuning

Implement GridSearchCV for n_estimators, max_depth, and learning_rate.
Add visualization for parameter sensitivity analysis.

Closes #42
```

```
fix(api): Handle rate limiting errors gracefully

Add exponential backoff retry logic for external API calls.
Prevent crashes when rate limits are exceeded.

Fixes #38
```

## README Quality Bar

### Minimum Requirements
- **Title & Description**: Clear project name and one-sentence summary
- **Problem Statement**: What problem does this solve?
- **Key Features**: 3-5 bullet points of main capabilities
- **Setup Instructions**: How to install dependencies and run the project
- **Usage Examples**: Code snippets or command-line examples
- **Tech Stack**: List of technologies, frameworks, and libraries used

### Recommended Additions
- **Architecture**: System design, data flow, or component overview
- **Results/Metrics**: Performance numbers, accuracy, user adoption
- **Limitations**: Known issues, constraints, or areas for improvement
- **Roadmap**: Future plans or potential enhancements
- **Contributing**: Guidelines for contributions (if open to collaboration)
- **License**: Clear license statement

### Advanced (for production projects)
- **Deployment Guide**: Step-by-step deployment instructions
- **API Documentation**: Endpoint descriptions, request/response examples
- **Testing**: How to run tests and expected coverage
- **Monitoring**: Logging, metrics, and observability setup
- **Troubleshooting**: Common issues and solutions

## Quick Assessment

**Pin if**: Demonstrates production-grade work, unique technical approach, or measurable impact.

**Showcase (unpinned) if**: Good code quality and documentation, but less unique or impactful.

**Archive if**: Incomplete, broken, superseded, or no longer relevant.

**Delete if**: Contains sensitive data, is a duplicate, or has no value.


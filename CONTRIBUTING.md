# Contributing to Shoppy Dashboard

First off, thank you for considering contributing to Shoppy Dashboard! It's people like you that make this project better for everyone.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Process](#development-process)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Community](#community)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to providing a welcoming and inclusive environment. By participating, you are expected to uphold this code.

### Our Standards

**Examples of behavior that contributes to a positive environment:**

- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

**Examples of unacceptable behavior:**

- The use of sexualized language or imagery
- Trolling, insulting/derogatory comments, and personal attacks
- Public or private harassment
- Publishing others' private information without permission
- Other conduct which could reasonably be considered inappropriate

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When creating a bug report, include as many details as possible:

**Bug Report Template:**

```markdown
**Describe the bug**
A clear and concise description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:

1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected behavior**
A clear and concise description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Environment:**

- OS: [e.g. Windows 11, macOS 14]
- Browser: [e.g. Chrome 120, Firefox 121]
- Node Version: [e.g. 18.17.0]
- npm Version: [e.g. 9.6.7]

**Additional context**
Add any other context about the problem here.
```

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

**Enhancement Template:**

```markdown
**Is your feature request related to a problem?**
A clear and concise description of what the problem is.

**Describe the solution you'd like**
A clear and concise description of what you want to happen.

**Describe alternatives you've considered**
A clear and concise description of alternative solutions or features.

**Additional context**
Add any other context or screenshots about the feature request.
```

### Your First Code Contribution

Unsure where to begin? You can start by looking through these issues:

- **Good First Issues** - issues that should only require a few lines of code
- **Help Wanted Issues** - issues that may be more involved

### Pull Requests

We actively welcome your pull requests! Here's how to contribute code:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'feat: add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Git

### Setup Development Environment

1. **Fork and clone the repository**

   ```bash
   git clone https://github.com/YOUR_USERNAME/dashboard-react.git
   cd dashboard-react
   ```

2. **Add upstream remote**

   ```bash
   git remote add upstream https://github.com/mnaimfaizy/dashboard-react.git
   ```

3. **Install dependencies**

   ```bash
   npm install
   ```

4. **Create a branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

5. **Start development server**
   ```bash
   npm start
   ```

## Development Process

### Branch Naming Convention

Use descriptive branch names that reflect the work being done:

- `feature/` - New features (e.g., `feature/add-user-authentication`)
- `fix/` - Bug fixes (e.g., `fix/sidebar-navigation-bug`)
- `docs/` - Documentation updates (e.g., `docs/update-readme`)
- `refactor/` - Code refactoring (e.g., `refactor/optimize-chart-rendering`)
- `test/` - Adding or updating tests (e.g., `test/add-button-tests`)
- `chore/` - Maintenance tasks (e.g., `chore/update-dependencies`)

### Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

**Types:**

- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation only changes
- `style:` Changes that don't affect code meaning (formatting, etc.)
- `refactor:` Code change that neither fixes a bug nor adds a feature
- `perf:` Performance improvement
- `test:` Adding or correcting tests
- `chore:` Changes to build process or auxiliary tools

**Examples:**

```bash
feat: add dark mode toggle to settings panel

fix: resolve sidebar collapse issue on mobile devices

docs: update installation instructions in README

refactor: extract chart logic into custom hook

test: add unit tests for Button component

chore: update React to version 18.3
```

### Keep Your Fork Updated

Regularly sync your fork with the upstream repository:

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

### Making Changes

1. **Make your changes** in your feature branch
2. **Follow the coding standards** (see below)
3. **Test your changes** thoroughly
4. **Update documentation** if needed
5. **Commit your changes** with clear commit messages

### Testing Your Changes

Before submitting a pull request:

```bash
# Run the app to verify it works
npm start

# Build the project to ensure no build errors
npm run build

# Run tests (if available)
npm test
```

**Manual Testing Checklist:**

- [ ] Test in Chrome, Firefox, and Safari
- [ ] Test responsive design (mobile, tablet, desktop)
- [ ] Test dark mode and light mode
- [ ] Test all affected routes/pages
- [ ] Verify no console errors or warnings
- [ ] Check that existing functionality still works

## Pull Request Process

### Before Submitting

- [ ] Your code follows the project's coding standards
- [ ] You've tested your changes thoroughly
- [ ] You've updated relevant documentation
- [ ] Your commits follow the commit message guidelines
- [ ] Your branch is up to date with the main branch
- [ ] There are no merge conflicts

### Submitting a Pull Request

1. **Push your changes** to your fork

   ```bash
   git push origin feature/your-feature-name
   ```

2. **Open a Pull Request** on GitHub

3. **Fill out the PR template** with:
   - Description of changes
   - Motivation and context
   - Type of change (bug fix, new feature, etc.)
   - Screenshots (if applicable)
   - Testing performed
   - Related issues

**Pull Request Template:**

```markdown
## Description

Brief description of what this PR does.

## Type of Change

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## How Has This Been Tested?

Describe the tests you ran and how to reproduce them.

## Screenshots (if applicable)

Add screenshots to help explain your changes.

## Checklist

- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have tested my changes in multiple browsers
- [ ] I have tested both light and dark modes
```

### Review Process

1. **Automated checks** will run on your PR
2. **Maintainers will review** your code
3. **Address feedback** by making additional commits
4. Once approved, a **maintainer will merge** your PR

### After Your PR is Merged

1. Delete your feature branch
2. Update your local main branch
3. Celebrate your contribution! 🎉

## Coding Standards

### JavaScript/React

1. **Use functional components** with Hooks

   ```jsx
   // Good
   const MyComponent = () => {
     const [state, setState] = useState(false);
     return <div>{state}</div>;
   };

   // Avoid class components
   ```

2. **Destructure props and context**

   ```jsx
   // Good
   const Button = ({ text, onClick, disabled }) => {
     return <button onClick={onClick}>{text}</button>;
   };
   ```

3. **Use meaningful variable names**

   ```jsx
   // Good
   const isUserAuthenticated = true;
   const handleFormSubmit = () => {};

   // Avoid
   const flag = true;
   const func = () => {};
   ```

4. **Keep components small and focused**
   - One component should do one thing
   - Extract complex logic into custom hooks
   - Break down large components

5. **Add comments for complex logic**
   ```jsx
   // Calculate discount based on user tier and cart value
   const calculateDiscount = (tier, cartValue) => {
     // Complex logic here
   };
   ```

### Styling

1. **Use Tailwind utility classes**

   ```jsx
   <div className="flex items-center justify-between p-4 bg-white dark:bg-gray-800">
   ```

2. **Always provide dark mode alternatives**

   ```jsx
   <p className="text-gray-900 dark:text-gray-100">
   ```

3. **Use responsive classes**

   ```jsx
   <div className="w-full md:w-1/2 lg:w-1/3">
   ```

4. **Leverage theme colors from context**
   ```jsx
   const { currentColor } = useStateContext();
   <button style={{ backgroundColor: currentColor }}>
   ```

### File Organization

- Place components in appropriate folders
- Export components from index files
- Keep related files together
- Use consistent naming conventions

### Performance

- Avoid unnecessary re-renders
- Use `useCallback` and `useMemo` when appropriate
- Lazy load routes and heavy components
- Optimize images and assets

## Community

### Getting Help

- **GitHub Issues**: For bugs and feature requests
- **Discussions**: For questions and general discussion
- **Documentation**: Check [DEVELOPMENT.md](DEVELOPMENT.md) for detailed guides

### Recognition

Contributors will be recognized in:

- GitHub contributors list
- Project documentation (if making significant contributions)
- Release notes (for notable features)

## Questions?

Don't hesitate to ask questions! You can:

- Open an issue with the `question` label
- Start a discussion in GitHub Discussions

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to Shoppy Dashboard! 🙏

# Code Formatter,  Linter for Python - Javascript

Using **linters** helps you enforce **consistent code style** in both your **frontend (JavaScript/React)** and **backend (Python)** projects.

Here’s how to set up **linters** for both stacks, with configs you can copy and use right away:

---

## **✅ 1. React + JavaScript/TypeScript**

**Tools:**

• **ESLint** – detects code issues and enforces style

• **Prettier** – auto-formats code

• Optional: eslint-plugin-react, eslint-config-airbnb, etc.

---

**✅ Install ESLint + Prettier (CRA)**

```
npm install eslint prettier eslint-plugin-react eslint-config-prettier eslint-plugin-import --save-dev
```

---
**✅ .eslintrc.json**

```
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "prettier"
  ],
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["react"],
  "rules": {
    "react/prop-types": "off",
    "no-unused-vars": "warn",
    "react/react-in-jsx-scope": "off"
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
```

---

**✅ .prettierrc**

```
{
  "semi": true,
  "singleQuote": true,
  "printWidth": 100,
  "trailingComma": "es5"
}
```

  

---

## **✅ 2.  Python**

  

**Tools:**

• **Black** – opinionated formatter (auto-style)

• **Flake8** – linter (code quality + unused imports/vars)

• Optional: **isort** – auto-sorts imports

---

**✅ Install (using pip)**

```
pip install black flake8 isort
```

---

**✅ Usage (Manual CLI)** 

```
black app/         # Format all code in "app"
flake8 app/        # Show lint issues
isort app/         # Sort imports
```

---

**✅ .flake8 config**

Create a .flake8 file in your project root:

```
[flake8]
max-line-length = 100
exclude = .git,__pycache__,env,venv,migrations
ignore = E203, E266, E501, W503, F403, F401
```

---

**✅ VS Code Integration - Automatic format when saved**

Install extensions:

• **ESLint**

• **Prettier - Code formatter**

• **Python** (for Black and Flake8)

  

Then in settings.json:

```
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  },
  "python.formatting.provider": "black",
  "python.linting.flake8Enabled": true
}
```

  

---

**✅ Summary Table**

|**Stack**|**Linter**|**Formatter**|**Config file**|
|---|---|---|---|
|React|ESLint|Prettier|.eslintrc.json, .prettierrc|
|Python|Flake8|Black|.flake8, pyproject.toml|

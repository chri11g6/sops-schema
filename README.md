# Sops Schema

A JSON Schema for validating `.sops.yaml` configuration files used with [Mozilla SOPS](https://github.com/mozilla/sops).

## 📖 Overview

**Sops Schema** provides a structured and machine-readable schema for `.sops.yaml`, helping developers:

- Validate their SOPS configuration files
- Improve IDE support with autocompletion and error detection
- Reduce misconfigurations and errors in secret management

This project aims to standardize the `.sops.yaml` format and make SOPS configuration more reliable and developer-friendly.

## 📂 Features

- ✅ JSON Schema specification for `.sops.yaml`
- ✅ Compatible with popular IDEs (e.g., VSCode, JetBrains) for schema-based validation
- ✅ Supports custom validation workflows and CI integration
- ✅ Open-source and community-driven

## 🔌 Usage

### 1. Reference the schema in your `.sops.yaml` file

You can use a `$schema` directive if your tool supports it (e.g., for IDE validation):

```yaml
# .sops.yaml
$schema: "https://raw.githubusercontent.com/chri11g6/sops-schema/refs/heads/master/sops.schema.json"

creation_rules:
  - encrypted_regex: '^(data|stringData)$'
    key_groups:
      - pgp: "your-key-id"
```

### 2. Validate using CLI tools (optional)

Use JSON/YAML schema validation tools like:

```bash
yaml-language-server --validate .sops.yaml
```

Or in CI:

```bash
yamllint -d "{extends: default, rules: {document-start: disable}}" .sops.yaml
```

## 📦 Installation

You can download the schema directly from this repo or host it on your own schema registry.

```bash
curl -O https://raw.githubusercontent.com/chri11g6/sops-schema/refs/heads/master/sops.schema.json
```

Or clone the repo:

```bash
git clone https://github.com/chri11g6/sops-schema.git
```

## 💬 Contributing

Contributions are welcome! Please open issues or submit pull requests to improve the schema or add support for additional SOPS features.
# Academic Paper All-in-One Template (IEEE / ACM / USENIX)

This repository provides a unified LaTeX environment for managing research papers across different conference formats (**IEEE**, **ACM**, and **USENIX**). It minimizes the effort required to re-format papers after a rejection or when targeting different conferences.

## 🚀 Key Features

* **Single Source of Truth**: Manage your content in one place and change formats with a single command.
* **Modular Structure**: Organized folder structure for sections, figures, and utilities.
* **Smart Build System**: Multi-target `Makefile` for automated PDF generation, font embedding, and submission zipping.
* **Quality Control**: Integrated spell-checking and font embedding verification.

---

## 📁 Project Structure

```text
.
├── main.tex              # Main entry point with target selection logic
├── Makefile              # Build automation script
├── ref.bib               # Bibliography file
├── figures/              # Images and plots
├── sections/             # Modular .tex files (abstract, intro, etc.)
├── utils/                # Custom commands and style tweaks
├── *.cls / *.sty / *.bst # Conference-specific format files
└── .gitignore            # Git exclusion rules

```

---

## 🛠 Prerequisites

Ensure you have the following installed:

* **LaTeX Distribution**: TeX Live (recommended) or MiKTeX.
* **Latexmk**: For automated multi-pass compilation.
* **Ghostscript (`ps2pdf`)**: For high-quality font embedding.
* **Aspell**: For the spell-checking feature.
* **pdffonts**: To verify font embedding status.

---

## 💻 Usage

### 1. Build PDF for Specific Target

You can build the paper for a specific conference without modifying the source code. The output PDF will be named `main_{target}.pdf`.

```bash
# Build for IEEE (default)
make ieee

# Build for ACM
make acm

# Build for USENIX
make usenix

```

### 2. General Commands

```bash
# Clean up all temporary build files
make clean

# Run spell check on all files in sections/
make spell

# Create a zip archive for submission (source files only)
make acm zip    # Creates source_main_acm.zip

```

---

## ⚙️ Configuration

### Adding Content

Write your content in the `sections/` directory. Use the following logic in `main.tex` or any sub-file to handle conference-specific commands:

```latex
\ifIEEE
    % IEEE-specific content/commands
\fi

\ifACM
    % ACM-specific content/commands
\fi

```

### Changing Bibliography

The template is set to use `ref.bib` by default. If you need to use different styles, the `Makefile` and `main.tex` automatically handle `\bibliographystyle` based on the selected target.

---

## 📝 License

Feel free to use and modify this template for your research projects. Good luck with your submissions!
Originally created by Jin Heo (@jheo4) and maintained at
https://github.com/PaperRepos/AIO_Template

---


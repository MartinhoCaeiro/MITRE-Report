**MITRE-Report**

- **Project:**: A LaTeX report about MITRE/ATT&CK, cyber threat intelligence, governance, and digital forensics. The main document is `LaTeX Report/Relatorio.tex`.
- **Author:**: Martinho José Novo Caeiro

**Contents**
- **Main report:**: `LaTeX Report/Relatorio.tex`
- **Bibliography:**: `LaTeX Report/Recursos/referencias.bib`
- **Logos and resources:**: `LaTeX Report/Recursos/Logos/`

**Requirements**
- **TeX distribution:**: TeX Live or MiKTeX (with `pdflatex`).
- **Biber:**: Required to process the bibliography (`biber`).
- **Optional:**: `latexmk` for a single-command build workflow.

**Build (Windows PowerShell)**
- Minimal manual sequence (works with MiKTeX/TeX Live + Biber):

```powershell
pdflatex -interaction=nonstopmode "LaTeX Report\Relatorio.tex";
biber "LaTeX Report\Relatorio";
pdflatex -interaction=nonstopmode "LaTeX Report\Relatorio.tex";
pdflatex -interaction=nonstopmode "LaTeX Report\Relatorio.tex";
```

- If you have `latexmk` installed, run:

```powershell
latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" -use-biber "LaTeX Report\Relatorio.tex"
```

**Notes**
- Images referenced in the document are inside `LaTeX Report/Recursos/Logos/`.
- If compilation fails due to missing packages, install them via your TeX distribution package manager.
- To clean auxiliary files (from PowerShell):

```powershell
Remove-Item "LaTeX Report\*.aux","LaTeX Report\*.bbl","LaTeX Report\*.blg","LaTeX Report\*.fdb_latexmk","LaTeX Report\*.fls","LaTeX Report\*.run.xml" -ErrorAction SilentlyContinue
```

**License**
- **License:** This repository is licensed under the GNU General Public License v3.0 (GPL-3.0).


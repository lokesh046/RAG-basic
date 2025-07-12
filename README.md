import nbformat

# Load the notebook
notebook_path = "/mnt/data/6866648c-0da3-4265-bab0-2111f26dd86b.ipynb"
with open(notebook_path, "r", encoding="utf-8") as f:
    nb = nbformat.read(f, as_version=4)

# Extract all code and markdown cells
cells = nb["cells"]
code_cells = [cell["source"] for cell in cells if cell["cell_type"] == "code"]
md_cells = [cell["source"] for cell in cells if cell["cell_type"] == "markdown"]

# Provide a preview of markdown and first code cell
md_preview = "\n\n".join(md_cells[:2])
code_preview = "\n\n".join(code_cells[:1])

md_preview, code_preview

# System Design

System design interview preparation slides using Marp.

## Setup

```bash
npm install
```

## Usage

### Convert single file

```bash
# PDF (output cùng thư mục)
npm run pdf slides/leetcode-system-design.md

# PDF với output path tùy chọn
npm run pdf slides/leetcode-system-design.md -- -o dist/leetcode.pdf

# HTML
npm run html slides/leetcode-system-design.md -- -o dist/leetcode.html

# Preview
npm run preview slides/leetcode-system-design.md
```

### Convert all slides

```bash
npm run slides:html   # All slides -> dist/*.html
npm run slides:pdf    # All slides -> dist/*.pdf
npm run slides:watch  # Watch mode, auto-rebuild
```

Output files will be generated in `dist/` folder.

## VS Code

Install recommended extension **Marp for VS Code** to preview slides directly in editor.

## Slides

| File                               | Description                           |
| ---------------------------------- | ------------------------------------- |
| `slides/leetcode-system-design.md` | Full LeetCode system design (7 steps) |
| `slides/example.md`                | Example template                      |

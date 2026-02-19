# Resume

A YAML-as-source resume repository that automatically renders to PDF using [RenderCV](https://github.com/sinaatalay/rendercv) on every push to main.

## 📁 Repository Structure

```
resume/
├── John_Doe_CV.yaml           # Your resume in YAML format
├── .github/
│   └── workflows/
│       └── render.yaml        # GitHub Actions workflow for automatic rendering
├── .gitignore                 # Ignores output files and PDFs
└── README.md                  # This file
```

## 🎨 About RenderCV

[RenderCV](https://github.com/sinaatalay/rendercv) is a LaTeX-based resume generator that takes a YAML file as input and produces a professional PDF resume. This repository uses the `engineeringresumes` theme, which is optimized for technical roles.

## ✏️ Editing Your Resume

### Online Editing (Easiest)

1. Click on `John_Doe_CV.yaml` in the GitHub repository
2. Click the pencil icon (✏️) to edit
3. Make your changes directly in the browser
4. Commit the changes to the `main` branch
5. The workflow will automatically trigger and generate a new PDF

### Local Editing

1. Clone the repository:
   ```bash
   git clone https://github.com/ljredmond9/resume.git
   cd resume
   ```

2. Edit `John_Doe_CV.yaml` with your preferred text editor:
   ```bash
   # Use any text editor you like
   nano John_Doe_CV.yaml
   # or
   vim John_Doe_CV.yaml
   # or open in VS Code
   code John_Doe_CV.yaml
   ```

3. Commit and push your changes:
   ```bash
   git add John_Doe_CV.yaml
   git commit -m "Update resume"
   git push origin main
   ```

## 🖥️ Local Rendering

To render your resume locally before pushing:

### 1. Install RenderCV

```bash
# Using pip
pip install rendercv[full]

# Or using pipx (recommended for CLI tools)
pipx install rendercv[full]
```

### 2. Render Your Resume

```bash
# Render the CV
rendercv render John_Doe_CV.yaml

# The output will be in the rendercv_output/ directory
```

### 3. View the Generated PDF

The rendered PDF will be located at:
```
rendercv_output/John_Doe_CV.pdf
```

You can open it with your system's default PDF viewer.

## 🚀 Automatic Publishing

Every time you push changes to the `main` branch:

1. **GitHub Actions** automatically triggers the render workflow
2. **RenderCV** generates a fresh PDF from your YAML file
3. The PDF is **uploaded as a workflow artifact** (downloadable from the Actions tab)
4. A **GitHub Release** tagged `latest` is created or updated with the new PDF attached

### Accessing Your Resume

- **Latest Release**: Go to the [Releases](../../releases/latest) page to download the most recent PDF
- **Workflow Artifacts**: Visit the [Actions](../../actions) tab and download from any workflow run

## 🎨 Customization

### Changing the Theme

RenderCV supports multiple themes. To change from `engineeringresumes` to another theme, edit the `design` section in `John_Doe_CV.yaml`:

```yaml
design:
  theme: classic  # or sb2nov, moderncv, etc.
  color: blue
  page_size: letterpaper
```

### Available Themes

- `classic` - Traditional academic CV style
- `sb2nov` - Popular single-column format
- `moderncv` - Modern two-column layout
- `engineeringresumes` - Optimized for engineering/tech roles (current)

### Customizing Content

The YAML file is organized into sections:

- **cv**: Basic information (name, contact details, summary)
- **sections**: Your resume sections (Experience, Education, Projects, Skills)
- **design**: Theme and styling options

Refer to the [RenderCV documentation](https://docs.rendercv.com/) for detailed customization options.

## 🔧 Manual Workflow Trigger

You can also manually trigger the render workflow:

1. Go to the [Actions](../../actions) tab
2. Click on "Render CV" workflow
3. Click "Run workflow" button
4. Select the `main` branch
5. Click "Run workflow"

## 📝 Tips

- Keep your YAML file properly indented (use 2 spaces)
- Test locally with `rendercv render` before pushing
- Use the `workflow_dispatch` trigger to manually regenerate without making code changes
- The workflow runs on every push to `main`, so commit messages are your changelog

## 🐛 Troubleshooting

### Rendering Fails

1. Check the [Actions](../../actions) tab for error details
2. Ensure your YAML syntax is correct (use a YAML validator)
3. Test rendering locally to catch errors early

### PDF Not Generated

1. Verify the workflow completed successfully in the Actions tab
2. Check that `John_Doe_CV.yaml` exists and is properly formatted
3. Look for error messages in the workflow logs

## 📄 License

This repository is provided as-is for personal use. Your resume content is your own.

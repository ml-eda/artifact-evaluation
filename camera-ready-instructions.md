# Including badges in your camera-ready paper MLCAD2024

### Step 1. Download the PDF badges from below and add it to your latex folder

[Available badge](acm_badges/artifacts_available_v1.1.pdf)

[Functional badge](acm_badges/artifacts_functional_v1.1.pdf)

### Step 2. Include the TikZ and Background packages.
    \usepackage{tikz}
    \usepackage[pages=some]{background}

### Step 3. Copy the following LaTeX code at right after \maketitle in your main LaTeX source file. Please only include the badges you are awarded. 
    \maketitle
    \backgroundsetup{opacity=1, scale=1, angle=0, contents={
    \begin{tikzpicture}[remember picture, overlay]
    \node[anchor=north east, inner xsep=50pt, inner ysep=10pt] at (current page.north east) {
    \href{https://www.acm.org/publications/policies/artifact-review-and-badging-current}{
    \includegraphics[width=50pt]{artifacts_available_v1.1.pdf}
    \includegraphics[width=50pt]{artifacts_evaluated_functional_v1.1.pdf}
    }};
    \end{tikzpicture}
    }}
    \BgThispage

### Example on how the badges should appear in your paper
[](example_acm_badges_in_paper.png)

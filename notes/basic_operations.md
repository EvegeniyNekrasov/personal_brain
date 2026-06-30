---
id: commit
aliases: []
tags: []
created: "30-06-2026"
---

# Commit

Commit hast same structure as blob and tree. It containt object type, object length and content of the object.

Each git commit has has: author name and email, commit description and parent (is optional) and has own sha1 hash.

Commit contains pointer to specific tree
```mermaid
---
config:
  theme: base
  flowchart:
    htmlLabels: true
---
flowchart TB

    C["<span style='color:#2e9b57'>8a31fb</span> &nbsp;&nbsp; <u>Commit</u><br/><br/>Author name and email<br/>Commit description<br/>Parent<br/><br/><div style='text-align:center'>3b95df</div>"]

    T["<span style='color:#2e9b57'>3b95df</span> &nbsp;&nbsp; <u>Tree</u><br/><br/><span style='color:#2e9b57'>file1.txt</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style='color:#2e9b57'>file2.txt</span>"]

    B1["<span style='color:#2e9b57'>b7aec5</span> &nbsp;&nbsp; <u>Blob</u><br/><br/>Hello, Git"]
    B2["<span style='color:#2e9b57'>4400aa</span> &nbsp;&nbsp; <u>Blob</u><br/><br/>Second file in Git repository"]

    R["Root<br/>directory"]

    C --> T
    T --> B1
    T --> B2

    %% Esto ayuda a mantener Root a la derecha del Tree
    T ~~~ R
    R -.-> T

    classDef commit fill:#dcebd7,stroke:#8db97a,stroke-width:2px,color:#111,rx:20,ry:20;
    classDef tree fill:#f7e4c8,stroke:#d6a03a,stroke-width:2px,color:#111,rx:20,ry:20;
    classDef blob1 fill:#dce7fa,stroke:#7b97c6,stroke-width:2px,color:#111,rx:20,ry:20;
    classDef blob2 fill:#eadff2,stroke:#9b83ae,stroke-width:2px,color:#111,rx:20,ry:20;
    classDef note fill:transparent,stroke:transparent,color:#111;

    class C commit
    class T tree
    class B1 blob1
    class B2 blob2
    class R note
```

Commit is an wrapper around tree object in git database.



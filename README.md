# aiml-archive

Collection of AI/ML experiments, notebooks, and example projects created in past 
## Contents
- Jupyter notebooks demonstrating small projects and experiments:
  - `image_colorization_cnn.ipynb` — image colorization experiment using a CNN
  - `logo_detection_yolo3.ipynb` — logo detection using a YOLOv3-based workflow
  - `sales_prediction_ml.ipynb` — sales forecasting / weekly-sales regression baseline using retail train/test datasets and tree-based models

The repository intentionally keeps each project self-contained. See each notebook for dataset notes, dependencies, and detailed instructions.

## Author
- Amit Jaiswar

## Project Timeline
- Initial development: Jan–Jul 2021
- Refactored and documented: 2026

## Git: resolving a diverged branch (fast-forward aborted)
If you see "Not possible to fast-forward, aborting." when pulling, try the following safe steps.

1) Inspect divergence
```bash
# fetch remote refs
git fetch origin
# commits on remote not in local
git log --oneline HEAD..origin/dev
# commits on local not in remote
git log --oneline origin/dev..HEAD
```

2) Recommended safe workflow (rebase local commits onto remote)
```bash
# make a local backup before rewrite
git branch backup-dev
# rebase your local dev onto the remote dev
git rebase origin/dev
# if conflicts occur: edit files, then
git add <resolved-files>
git rebase --continue
# after successful rebase, push (history was rewritten)
git push --force-with-lease origin dev
```

3) Alternative: merge remote into local (keeps both histories)
```bash
git merge origin/dev
# resolve conflicts if any, commit, then
git push origin dev
```

4) If uncertain, open a PR or keep the backup branch and inspect changes before force-pushing.

Notes:
- Use --force-with-lease to avoid clobbering others' work.
- If working with collaborators, prefer merge or coordinate before forcing a push.

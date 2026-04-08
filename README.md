# History of Science — Generals Field Map

Interactive visualization of the HoS generals reading list. Plots books on two axes:
- **X-axis**: Year published (the evolving historiography)
- **Y-axis**: Historical period covered (the history itself)

Dots are colored by **geography**. Filter by **intellectual current** (SSK, instruments, empire, etc.) using the theme chips.

## File structure

```
index.html          ← the visualization (open in browser)
data/
  books.csv         ← edit this to add/modify books
  connections.csv   ← edit this to add/modify connections between books
```

## How to edit

**books.csv** columns:
| Column | Description | Example |
|--------|-------------|---------|
| `id` | Unique integer | `1` |
| `author` | Last name(s) shown on chart | `Shapin & Schaffer` |
| `title` | Full title | `Leviathan and the Air-Pump` |
| `year_published` | Publication year | `1985` |
| `hist_start` | Earliest year the book covers | `1650` |
| `hist_end` | Latest year the book covers | `1670` |
| `geography` | Primary geographic focus | `europe` |
| `currents` | Intellectual currents, pipe-separated | `construction\|material\|statepower` |
| `description` | One-sentence summary | `"Solutions to the problem of knowledge..."` |

**Geography values**: `europe`, `north_america`, `latin_america`, `caribbean`, `africa`, `east_asia`, `south_asia`, `russia`, `transatlantic`, `global`

**Current values**: `epistemology`, `construction`, `material`, `statepower`, `bodies`, `circulation`, `empire`, `nature`

**connections.csv** columns: `source_id`, `target_id`, `label`

## Running locally

Browsers block CSV loading from `file://` URLs. Use a local server:

```bash
cd /path/to/this/folder
python3 -m http.server 8000
# then open http://localhost:8000
```

## Hosting on GitHub Pages

1. Push this repo to GitHub
2. Go to Settings → Pages → Source: main branch, root folder
3. Your map will be live at `https://yourusername.github.io/repo-name/`

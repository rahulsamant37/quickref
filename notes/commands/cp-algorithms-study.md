# CP-Algorithms Study Quickref

Use with: `qref cpa`

## Main Commands Only

| Goal | Command |
|---|---|
| Open action picker (best entry point) | `cpa` |
| Read-first track | `cpa read` |
| Revise-later track | `cpa revise` |
| Open roadmap | `cpa roadmap` |
| Open weekly plan | `cpa weekly` |
| Show read-first list | `cpa list-read` |
| Show revise list | `cpa list-revise` |

## Fast Open Variants

| Goal | Command |
|---|---|
| Direct read command | `cpa-read` or `cp-read` |
| Direct revise command | `cpa-revise` or `cp-revise` |
| Short aliases | `cpr` and `cpv` |

## Daily Navigation Flow

1. `cpa roadmap`
2. `cpa read`
3. Study one article
4. `cpa weekly` for schedule check
5. `cpa revise` for revision slot

## Most Useful Filters

| Goal | Command |
|---|---|
| Find by keyword | `cpa-read dijkstra` |
| Show only matches | `cpa-read -q graph -l` |
| Open by order number | `cpa-read --index 12` |
| Surprise practice | `cpa-read --random` |

## Tab Completion

- Type `cpa-read` then press `Tab` to autocomplete flags and topic names.
- Type `cpa` then press `Tab` to autocomplete modes like `read`, `revise`, `roadmap`, `weekly`.

## Neovim Quick Access

| Goal | Command |
|---|---|
| Open roadmap | `:CPARoadmap` |
| Open weekly plan | `:CPAWeeklyPlan` |
| Open read list | `:CPAReadList` |
| Open revise list | `:CPAReviseList` |

Keymaps:

- `<leader>ar` roadmap
- `<leader>aw` weekly
- `<leader>al` read list
- `<leader>aL` revise list

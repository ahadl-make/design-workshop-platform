# Backstage UI (BUI) context pack, v0.18.0

For AI tools building a rough single-file HTML prototype of a Make Backstage page. Everything below was checked against the `@backstage/ui@0.18.0` type definitions, and the starred (*) components were rendered in a browser. Do not browse; do not invent components or props. Start from `bui-starter.html`.

## 1. Rules

1. Use ONLY components and props listed in this file. If something is missing (see section 6), use plain HTML + `--bui-*` tokens.
2. Colours only via `--bui-*` tokens (`color: var(--bui-fg-secondary)`). No hex values in components. Make accent overrides live only in the starter's `:root` block.
3. Hardcode all data (arrays in the script). No fetch, no backend.
4. One primary Button per view. Everything else `variant="secondary"` or `"tertiary"`. A repeated per-row action ("Open") is `variant="secondary" size="small"`.
5. Build inside the starter's content area only. Keep sidebar and page header. Change `PAGE_TITLE` and `ACTIVE_NAV`.
6. Spacing via props (`p="4"`, `gap="3"`) or `var(--bui-space-N)`. Keep to the Make page anatomy in section 5; do not invent a new navigation model.

## 2. Loading (already wired in bui-starter.html; do not change the import map)

- CSS from jsdelivr; React 18.3.1, react-dom, htm and `@backstage/ui` via import map (esm.sh). The `&bundle=all` on the BUI URL is required, otherwise Tabs, Select, Table and Tag crash.
- Import components you use: `import { Flex, Card, CardBody, Text, Button } from '@backstage/ui';`
- JSX-free templates with htm. Component = `<${Name}>` and closer `<//>`:
  `html\`<${Button} variant="primary" onPress=${() => setX(1)}>Claim<//>\``
- Use `className=` (not `class=`) and style OBJECTS: `style=${{ color: 'var(--bui-fg-secondary)' }}`. A style string crashes React.
- BUI is built on React Aria: events are `onPress` (Button, ButtonIcon, Card, ToggleButton), `onChange` (fields, Switch, Checkbox, SearchField gives the string), `onSelectionChange` (Select, Tabs, Combobox give the key; **ToggleButtonGroup gives a Set of keys** — see its entry). Use `isDisabled`, `isSelected`, `isRequired`, not `disabled`.
- Every field without a visible `label` needs `aria-label`.
- No icon set is bundled. `iconStart`/`icon` take any React element, e.g. an inline `<svg>` (see `icon()` in the starter) or a short text glyph.

## 3. Make styling

| Make | Value | How it is applied |
|---|---|---|
| Primary | #6d00cc (hover #5a00a8, pressed #440080) | starter `:root` sets `--bui-bg-solid`, `-hover`, `-pressed`, `--bui-accent-bg`, `--bui-ring`. Primary Button, focus ring inherit it. |
| Sidebar | `linear-gradient(180deg, #b55dcd 0, #724ebf 100%)`, white text | `--make-sidebar-bg` + `--bui-white`, in the shell |
| Page header title | #172B4D | `--make-title` (shell `<h1>`) |
| Links | #6d00cc | `--make-link`, applied to `.bui-Link` |
| Page background | light grey | `--bui-bg-app` |
| Cards, table, header | white | `--bui-bg-neutral-1` |
| Borders | light grey | `--bui-border-1` (strong: `--bui-border-2`) |

Status colours in Make screens (use `Text color`, tokens below): Ready/Healthy/Unlocked = `success` (green), Claimed = purple (`var(--bui-accent-bg)`), Paused/Pending = `secondary` grey, Failed/Locked = `danger`.

### Tokens (real names from styles.css)
- Surfaces: `--bui-bg-app`, `--bui-bg-neutral-1..4` (each has `-hover`, `-pressed`, `-disabled`), `--bui-bg-solid(-hover/-pressed/-disabled)`, `--bui-bg-info|success|warning|danger`
- Text: `--bui-fg-primary`, `--bui-fg-secondary`, `--bui-fg-disabled`, `--bui-fg-solid`, `--bui-fg-info|success|warning|danger`, `--bui-fg-positive|negative`
- Border: `--bui-border-1`, `--bui-border-2`, `--bui-border-info|success|warning|danger`; focus `--bui-ring`
- Spacing: `--bui-space-1..14` (space-4 = 16px, 1 unit = 4px). Radius: `--bui-radius-1..6`, `--bui-radius-full`
- Font: `--bui-font-regular`, `--bui-font-monospace`, `--bui-font-size-1..10`, `--bui-font-weight-regular|bold`
- Other: `--bui-shadow`, `--bui-white`, `--bui-black`, `--bui-gray-1..11`, `--bui-accent-bg`, `--bui-announcement-*` (banner-like surfaces), `--bui-positive-*`, `--bui-negative-*`, `--bui-warning-*` (`-bg`, `-fg`, `-border`, `-bg-subdued`)

## 4. Components

Responsive props accept `value` or `{ initial: v, md: v2 }`. Space values are strings: `"0.5" "1" ... "14"`.

### Layout
- **Box*** `bg`(`neutral|danger|warning|success`), `as`(html tag), `p/px/py/pt/pb/pl/pr`, `m/mx/my/mt/mb/ml/mr`, `display`, `position`, `width/minWidth/maxWidth/height/minHeight/maxHeight`, `grow/shrink/basis`. `html\`<${Box} p="4" bg="neutral">...<//>\``
- **Flex*** `direction`(`row|column|row-reverse|column-reverse`), `gap`, `align`(`start|center|end|baseline|stretch`), `justify`(`start|center|end|between`) + space props. `<${Flex} gap="3" align="center" justify="between">`
- **Grid*** is compound: `Grid.Root` (`columns="1".."12"|"auto"`, `gap`) and `Grid.Item` (`colSpan`, `colStart`, `colEnd`, `rowSpan`). `<${Grid.Root} columns="3" gap="4"><${Grid.Item}>...<//><//>`
- **Container*** page-width wrapper; props `my mt mb py pt pb`. **FullPage** `<main>` filling the viewport. **VisuallyHidden** screen-reader-only text.

### Surfaces
- **Card*** with **CardHeader**, **CardBody**, **CardFooter** (all just take children). Card is static by default; clickable via `onPress` + `label`, or link via `href` + `label` (+`target`). Also `grow/shrink/basis`.
  `<${Card}><${CardHeader}><${Text} variant="title-small">Title<//><//><${CardBody}>...<//><//>`
- **Accordion*** `<Accordion><AccordionTrigger title subtitle /><AccordionPanel>..` ; **AccordionGroup** (`allowsMultiple`) wraps several. Accordion `defaultExpanded`/`isExpanded`.
- **Dialog*** inside **DialogTrigger**: `<${DialogTrigger}><${Button}>Open<//><${Dialog}><${DialogHeader}>Title<//><${DialogBody}>..<//><${DialogFooter}><${Button} slot="close">Close<//><//><//><//>`. Dialog `width`, `height`, `isOpen`, `onOpenChange`.
- **Popover** `hideArrow`, `placement`; **Tooltip** inside **TooltipTrigger** (`<${TooltipTrigger}><${Button}>..<//><${Tooltip}>Hint<//><//>`).

### Typography
- **Text*** (there is no Heading component; use `as="h1".."h6"`). `variant`: `title-large|title-medium|title-small|title-x-small|body-large|body-medium|body-small|body-x-small`. `color`: `primary|secondary|danger|warning|success|info`. `weight`: `regular|bold`. `as`: `h1-h6|p|span|label|div|strong|em|small|legend`. `truncate`.
  `<${Text} variant="body-small" color="secondary">Updated 52m ago<//>`
- **Link*** (`href`, `variant`, `weight`, `color`, `standalone`, `truncate`). Purple via starter CSS. `<${Link} href="#">See the docs<//>`

### Actions
- **Button*** `variant`: `primary|secondary|tertiary`; `size`: `small|medium`; `destructive`; `iconStart`/`iconEnd` (element); `isDisabled`; `isPending`/`loading`; `onPress`. Default variant is primary (set it explicitly).
- **ButtonIcon*** icon-only: `icon`(element), `aria-label` (required), `variant`, `size`. For row actions use `variant="tertiary"`.
- **ButtonLink** button-looking anchor: `href`, `variant`, `size`, `iconStart/End`.
- **ToggleButton** (`isSelected`, `onChange`, `size`, `iconStart`) and **ToggleButtonGroup*** (`selectionMode="single|multiple"`, `disallowEmptySelection`, `selectedKeys` (array or Set), `onSelectionChange(keys: Set)`). Good for All / Public / Sign-in required chips. Copy-paste (tested):
  `<${ToggleButtonGroup} selectionMode="single" disallowEmptySelection selectedKeys=${[f]} onSelectionChange=${(ks) => setF([...ks][0])}>${OPTS.map((o) => html\`<${ToggleButton} key=${o.id} id=${o.id}>${o.label}<//>\`)}<//>`
- **MenuTrigger / Menu / MenuItem / MenuSection / MenuSeparator*** : `<${MenuTrigger}><${ButtonIcon} aria-label="Actions" icon=${...} /><${Menu}><${MenuItem} onAction=${fn}>Open<//><${MenuItem} color="danger">Delete<//><//><//>`. MenuItem props: `iconStart`, `color`(`primary|danger`), `href`. Also `SubmenuTrigger`, `MenuListBox`, `MenuAutocomplete`.

### Forms (label via `label`, optional `description`, `secondaryLabel`; `size`: `small|medium`)
- **TextField*** `label placeholder type(text|email|tel|url) icon value onChange isRequired isDisabled isInvalid`. **TextAreaField** (+`rows`), **NumberField**, **PasswordField**.
- **SearchField*** `placeholder size icon value onChange(string) startCollapsed aria-label`. For the filter row.
- **Select*** `options=${[{ value: 'all', label: 'Status: All' }, ...]}` (or `{id,label,description}`), `label`, `placeholder`, `selectedKey`, `defaultSelectedKey`, `onSelectionChange(key)` (key equals `value`), `searchable`, `selectionMode="multiple"`, `isDisabled`. Use `aria-label` when no `label`.
- **Combobox** same options API plus typing: `options`, `search`, `selectedKey`, `onSelectionChange`.
- **Checkbox*** (children = label, `isSelected`, `onChange`), **CheckboxGroup** (`label`, `orientation`), **RadioGroup** + **Radio** (`value`), **Switch*** (`label`, `isSelected`, `onChange`), **Slider**, **DatePicker**, **DateRangePicker**. **FieldLabel** for custom fields.

### Navigation
- **Tabs*** : `<${Tabs} selectedKey onSelectionChange><${TabList}><${Tab} id="devboxes">Devboxes<//><${Tab} id="keys">API Keys<//><//><${TabPanel} id="devboxes">...<//><${TabPanel} id="keys">...<//><//>`. Tab `id` is required and must match its TabPanel. Tab also accepts `href`.
- **Header*** (BUI page header with tabs): `title`, `description`, `tags=[{label,href?}]`, `metadata=[{label,value}]`, `tabs=[{id,label,href}]` (links, not panels), `activeTabId`, `breadcrumbs=[{label,href}]`, `customActions`, `sticky`. Same as **HeaderPage**. **PluginHeader** is a toolbar variant (`title`, `icon`, `tabs`, `customActions`). The starter already has a plain page header; use `Header` only if you need metadata/tabs, and then drop the starter `<h1>` row. **HeaderMetadataStatus** (`label`, `color: success|warning|danger|info`) and **HeaderMetadataUsers** (`users=[{name,src}]`) are for `metadata` values.
- **List*** : **List** + **ListRow** (`description`, `icon`, `menuItems`, `customActions`) for simple link/item lists.

### Data display
- **Table*** (high-level, recommended). Props: `columnConfig`, `data` (items need unique `id`), `pagination` (REQUIRED: `{ type: 'none' }` or `{ type: 'page', pageSize, hasNextPage, hasPreviousPage, onNextPage, onPreviousPage, totalCount, offset }`; `pageSize` must be 5, 10, 20, 30, 40 or 50, otherwise it silently falls back to 5. For a short hardcoded list use `{ type: 'none' }`), `sort={{ descriptor, onSortChange }}`, `rowConfig={{ onClick(item), getHref(item) }}`, `selection={{ mode, selected, onSelectionChange }}`, `emptyState`, `loading`, `error`.
  Column: `{ id, label, cell: (row) => element, isRowHeader, isSortable, width, minWidth }`. `cell` MUST return `Cell`, `CellText` or `CellProfile`:
  `{ id: 'name', label: 'Name', isRowHeader: true, cell: (r) => html\`<${CellText} title=${r.name} description=${r.desc} href="#" />\` }`
  Custom content: `cell: (r) => html\`<${Cell}><${Text} color="success">${r.status}<//><//>\``. `CellText`: `title`, `description`, `color`(`primary|secondary`), `leadingIcon`, `href`. `CellProfile`: `name`, `src`, `description`, `href`.
  `Cell` may contain `Badge`, `Text`, `ButtonLink` or `Button` (row action). An action column may have `label: ''`. `emptyState` takes any element, e.g. `html\`<${Flex} direction="column" gap="2" p="6"><${Text}>No apps match<//><//>\``.
- Low-level building blocks: **TableRoot, TableHeader, TableBody, Column, Row, Cell, TablePagination, TableBodySkeleton**; `useTable` hook for sorting/filtering/search state. Prefer `Table`.
- **Badge*** neutral pill, `size: small|medium`, `icon`. No colour variants (colour the text with `Text color` next to it).
- **Tag*** must be inside **TagGroup** (`<${TagGroup}><${Tag} id="a">Name<//><//>`); `size`, `icon`, `href`. Outside a TagGroup it crashes. Inside a Table cell use Badge, not Tag.
- **Avatar*** `src`, `name` (required), `size: x-small|small|medium|large|x-large`.

### Feedback
- **Alert*** `status: info|success|warning|danger`, `title`, `description`, `icon`(true or element), `customActions` (put a Button/Link here), `loading`. Use as the dismissible-looking announcement banner (no built-in dismiss: add a `ButtonIcon` in `customActions`).
- **Skeleton*** `width`, `height`, `rounded`. Loading placeholder. Buttons take `loading`.

## 5. Make Backstage page recipes (shell = starter sidebar + page header)

**Filter row (any page):** `Flex gap="3" align="center"` with the SearchField wrapped in `Box minWidth="280px" grow="1"` so it doesn't collapse on narrow screens; Selects / ToggleButtonGroup after it.

- **Home**: header "Welcome to Backstage, name!" → Alert (info, with primary Button "Manual setup" in `customActions`) → `Grid.Root columns="3"` of Cards: "Your AI spend" (empty text), "Toolkit" (grid of icon + label Links), "Your open pull requests" (empty state text).
- **Docs**: filter column left (Cards or Boxes: Owned/Starred/All counts as ToggleButtons, Owner and Tags `Select`) + right Card containing SearchField and Table (Document `CellText` with description, Owner Link, Kind, Type, actions `ButtonIcon` share/star).
- **Devboxes**: header with Owner/Lifecycle meta → Tabs (Devboxes, API Keys) → two promo Cards side by side (terminal hint with code, and "3 pre-warmed devboxes ready" with primary Button "Claim a devbox" + secondary "Create custom...") → filter row (SearchField + Selects "Status: All", "Claimed by: Anyone") → Table (name link, status Text colour, claimed by, archetype Badge, services, updated, row `ButtonIcon`/Menu). Group rows by "Available pool" and "Claimed by others" with two Tables or `Text variant="body-x-small"` section labels.
- **Deployments**: filter row (Selects Team, Repo) → matrix Table: first column service name + owner, per-environment columns showing health (`Text color="success"` Healthy), build `#433`, time, Badge for version, "Pending" secondary. Dense; show 4-6 services, 5-6 environments.
- **Kargo**: header with Owner/Lifecycle; action row (secondary Buttons "Lock all", "Unlock all", tertiary "Refresh") → Card with title "Projects" + SearchField → Table (project link, status Badge, locked by, reason, since, mode `ToggleButtonGroup` Automated/Manual).
- **AI spend**: filter row (Selects Month, Scope + "Last sync" Text) → `Grid.Root columns="4"` stat Cards (label `Text color="secondary"` + big `Text variant="title-large"`) → Card "Top 20 spenders" with Table (rank, developer, per-provider spend, counted spend, limit, usage).
- **Vibe Coded Apps**: intro Text → three stat Cards (All apps / Your apps / Public, first selected) → Alert info → toolbar (SearchField, ToggleButtonGroup All/Public/Sign-in required, Switch "Show addresses", primary Button "Import an app") → empty-state Card ("No apps are linked to you yet", primary Button) → Table (app Link, owner `CellProfile`, "Who can open it" Badge, last updated, Details Link).

## 6. Known gaps and caveats

- No Sidebar, app shell, Heading, Icon set, Spinner/ProgressBar, Toast, dedicated EmptyState or stat/KPI card, code block, or coloured status Badge/Tag in 0.18.0. The starter provides a plain-HTML sidebar and page header. Build empty states and stat cards from Card + Text; status colour from `Text color`.
- Header `tabs` render links (`href`), not panels; for in-page switching use `Tabs`.
- Table `Cell` content has no `Tag` (needs TagGroup); use Badge or Text.
- Icons: inline SVG or glyphs only.
- Make's production repo currently uses `@backstage/ui` 0.13.2 and mostly Material UI v4. These prototypes use 0.18.0, so props (Table API, Select `options`, Header, Alert `status`, `loading`) may differ when ported. Treat the prototype as a design artefact, not copy-paste code.

## 7. Docs

Component docs and examples for tools that can browse: https://ui.backstage.io/

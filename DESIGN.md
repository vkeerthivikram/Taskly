---
name: Taskly
description: A calm offline workbench for personal tasks.
colors:
  primary: "#0f766e"
  primary-hover: "#0b625c"
  primary-tint: "#e2f2ef"
  canvas: "#f5f7f9"
  surface: "#fff"
  rail: "#f0f3f5"
  ink: "#19292e"
  muted: "#5e707b"
  line: "#dde4e8"
  danger: "#b52e3a"
  danger-tint: "#fff0f1"
  dark-primary: "#70d5c5"
  dark-primary-hover: "#8ce2d4"
  dark-primary-tint: "#203f3d"
  dark-canvas: "#151f24"
  dark-surface: "#1d292f"
  dark-rail: "#18242a"
  dark-ink: "#e4edef"
  dark-muted: "#a0b2ba"
  dark-line: "#33454e"
  dark-danger: "#ffadb5"
  dark-danger-tint: "#492830"
  dark-on-primary: "#112e2b"
typography:
  headline:
    fontFamily: '"Segoe UI", system-ui, -apple-system, sans-serif'
    fontSize: "28px"
    fontWeight: 650
    lineHeight: 1.2
    letterSpacing: "-0.025em"
  title:
    fontFamily: '"Segoe UI", system-ui, -apple-system, sans-serif'
    fontSize: "14px"
    fontWeight: 600
    lineHeight: 1.5
  body:
    fontFamily: '"Segoe UI", system-ui, -apple-system, sans-serif'
    fontSize: "14px"
    lineHeight: 1.5
  label:
    fontFamily: '"Segoe UI", system-ui, -apple-system, sans-serif'
    fontSize: "12px"
    fontWeight: 500
rounded:
  tag: "4px"
  filter: "7px"
  control: "8px"
  lane: "10px"
  card: "12px"
  dialog: "14px"
spacing:
  compact: "8px"
  control-gap: "10px"
  related: "12px"
  group: "16px"
  section: "24px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.surface}"
    rounded: "{rounded.control}"
    padding: "8px 14px"
  button-primary-hover:
    backgroundColor: "{colors.primary-hover}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.control}"
    padding: "8px 14px"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.control}"
    padding: "8px 14px"
  input:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    rounded: "{rounded.control}"
    padding: "10px 12px"
  navigation-selected:
    backgroundColor: "{colors.primary-tint}"
    textColor: "{colors.primary}"
    rounded: "{rounded.control}"
    padding: "11px 12px"
  task-card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.card}"
    padding: "16px 14px"
  tag:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.muted}"
    rounded: "{rounded.tag}"
    padding: "2px 6px"
  status-chip-selected:
    backgroundColor: "{colors.primary-tint}"
    textColor: "{colors.primary}"
    rounded: "{rounded.filter}"
    padding: "8px 12px"
---

# Design System: Taskly

## Overview

**Creative North Star: "The Calm Workbench"**

Taskly is clean, calm, and restrained. Neutral surfaces carry the work; teal identifies actions and selected states. Compact controls, open task cards, and quiet metadata keep task titles and the next action easy to find.

This record captures the implemented offline app in `Taskly.html`, including its final CSS overrides. Runtime screenshots in `design/` provide visual evidence; `design/provenance.md` distinguishes them from the generated concept. Source code owns measurements and states. The north-star phrase summarizes the settled direction rather than adding a new brand commitment.

**Key Characteristics:**

- Neutral tonal layers with a single teal action accent.
- Compact controls and readable task titles.
- Thin borders, restrained corners, and functional depth.
- Matching light and dark themes with responsive task navigation.

## Colors

The palette combines cool neutrals with muted teal; the dark theme shifts teal lighter to preserve selected-state clarity. Frontmatter values are normative.

### Primary

- **Workbench Teal:** primary buttons, selected navigation, active tabs, checklist progress, and today's deadline label. Its hover companion strengthens the action; its tint supplies selected surfaces.
- **Dark Workbench Teal:** the same roles in dark mode, paired with a dark foreground on filled primary buttons.

### Neutral

- **Cool Canvas:** board background and field interiors.
- **Paper Surface:** header, cards, dialogs, and secondary controls.
- **Quiet Rail:** sidebar and subdued hover surfaces.
- **Deep Ink / Muted Ink:** titles and body text / metadata, counters, and supporting copy.
- **Soft Line:** borders, separators, and unfilled progress tracks.
- Dark variants retain these role assignments rather than inverting every color mechanically.

Danger and danger tint signal overdue dates, failed saves, errors, and destructive controls. Project and workflow dots are user-configurable categorical data; their individual colors are not brand primitives.

**The Action Accent Rule.** Use teal to communicate action, selection, or progress; keep ordinary surfaces neutral.

## Typography

The native stack is deliberate for this self-contained offline app: Segoe UI on Windows, then system UI fallbacks. It avoids remote font dependencies. It is not a display-font prescription for future unrelated pages.

- **Headline:** workspace title; its compact tracking establishes hierarchy. At the phone breakpoint it becomes (24px).
- **Title:** task title, with semibold weight and wrapping; final CSS uses (14px) across sizes.
- **Body:** base interface reading text. Buttons and ordinary inputs use (13px); project and task metadata use (12px).
- **Label:** field labels and supporting controls. Section labels are (11px), weight (650), with tracking (0.09em).
- The editor title is (23px), weight (600), line height (1.4). The focus timer alone uses large tabular numerals (58px; 52px on phones).

No decorative display role is implemented. Do not infer a new type scale from isolated timer or dialog values.

## Layout

The desktop app uses a fixed left rail (224px) and a workspace with a surface-colored header above the cool canvas. The header holds context, search, creation, view tabs, utilities, and filters. Content padding is (24px); board lanes have a (16px) gap and minimum column width (206px). The default five-column workflow is configurable, not a fixed design invariant. Lanes remain open on the canvas rather than becoming separate filled panels.

At (1100px) and below, the rail becomes (200px) and controls tighten. At (800px) and below, navigation moves off canvas with an overlay; the workspace loses its left margin. At (540px) and below, the header stacks, filters collapse behind a control, horizontal status chips select one visible board lane, cards gain padding (18px 16px), and a fixed footer keeps task creation available. The editor becomes full width. At (1600px) and above, minimum lane width grows to (240px).

The task editor is a right-hand drawer (480px) with a scrollable body and persistent footer. Ordinary dialogs are centered (520px; settings 620px), bounded by viewport dimensions. Long task titles wrap anywhere; navigation labels truncate while retaining their button label.

## Elevation & Depth

The workbench uses tonal layering and thin borders at rest. Cards have no resting shadow; hover changes their border to teal. Dialogs and toast notices alone use the shared ambient shadow. The backdrop dims context so the editor or decision remains clear. Exact light and dark shadow values live in the sidecar.

**The Working Surface Rule.** Keep task surfaces flat; reserve shadow for overlaid interaction.

## Shapes

Compact tags use the smallest corners; controls use gentle corners; cards and dialogs soften progressively. Circle completion controls and project/status dots communicate state without adding ornamental shapes. The desktop drawer meets the viewport edge with square corners. Most boundaries use a thin (1px) stroke.

## Components

- **Buttons:** primary teal, neutral bordered secondary, and transparent ghost variants. Standard controls have minimum height (40px); compact variants use (32px). Disabled controls lower opacity to (.45). Dark primary buttons use dark text.
- **Fields and search:** cool canvas fill, thin border, and control corners. Fields change border to teal on focus; search uses a teal border and tinted focus-within ring in place of the inner input outline. Other controls retain the global keyboard outline. Native selects preserve familiar input behavior.
- **Navigation:** icon, readable label, optional count; selected rows use teal text and tint. Rows have minimum height (44px). Mobile navigation preserves these styles inside the collapsed rail.
- **View tabs and status chips:** desktop view tabs use a teal underline and semibold active text. Phone workflow chips use bordered neutral buttons with teal tint and border when selected; counts remain adjacent to labels.
- **Task cards:** title and completion control lead; project, priority, dates, tags, and checklist progress support them. Completion adds a filled circle and title strikethrough. Drag feedback lowers card opacity and outlines the destination lane. Metadata remains subordinate to the title.
- **Tags and deadlines:** compact neutral tags identify user text. Today's deadline uses teal tint; overdue uses danger tint plus explicit text, so color is not the only cue.
- **Task action menu:** right-click or the three-dot control opens a cursor/trigger-positioned popup (236px) with compact (38px minimum) rows, inline SVG icons, grouped actions, and viewport clamping. Move-to uses a second menu view with the same pattern. It shares surface, accent, danger, and overlay-shadow tokens. Arrow keys, Escape, and visible focus support keyboard use; touch uses the three-dot control.
- **Editor and notices:** the drawer shares dialog surfaces and form controls. Toasts use ink as background, surface-colored text, and an inline undo action when available.

Global keyboard focus uses a teal outline (3px), offset (3px) on controls. Motion is brief: card border changes (160ms), mobile rail translation (200ms). Reduced-motion preference removes transitions and animations. These are functional feedback, not decorative choreography.

## Do's and Don'ts

### Do:

- **Do** keep teal tied to actions, selected states, and progress.
- **Do** preserve title-first task hierarchy with quiet supporting metadata.
- **Do** use the paired dark-theme roles rather than copying light-theme values.
- **Do** retain visible keyboard focus and reduced-motion behavior.
- **Do** treat source measurements and runtime captures as evidence for this app.

### Don't:

- **Don't** add resting shadows or heavy filled panels to every task lane.
- **Don't** turn configurable project or status colors into brand tokens.
- **Don't** promote the five-lane default or desktop composition into a rule for every future surface.
- **Don't** require external fonts or image assets for this offline app.
- **Don't** treat synthesized sidecar tonal ramps as implemented color tokens.

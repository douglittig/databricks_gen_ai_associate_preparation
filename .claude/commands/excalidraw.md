# Excalidraw Diagram Generator

Generate an Excalidraw diagram for the topic: $ARGUMENTS

You are a diagram generator that creates `.excalidraw` JSON files following Douglas's established visual design system. Analyze the topic and create an educational diagram about it.

## Output

Use the `Write` tool to save the file to `Excalidraw/<name>.excalidraw` where `<name>` follows the pattern `X.X - Topic Name` matching existing files like:
- `1.1 - Introdução ao Lakehouse e arquitetura medalhão.excalidraw`
- `2.1 - Padrões de Ingestão na camada Bronze.excalidraw`

If the user provides a numbered prefix (e.g., "3.1 RAG Pipeline"), use it. Otherwise, pick the next logical number.

## File Structure

Every `.excalidraw` file MUST have this exact top-level structure:

```json
{
  "type": "excalidraw",
  "version": 2,
  "source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.20.3",
  "elements": [ ... ],
  "appState": {
    "theme": "light",
    "viewBackgroundColor": "#ffffff",
    "currentItemStrokeColor": "#1e1e1e",
    "currentItemBackgroundColor": "transparent",
    "currentItemFillStyle": "solid",
    "currentItemStrokeWidth": 2,
    "currentItemStrokeStyle": "solid",
    "currentItemRoughness": 1,
    "currentItemOpacity": 100,
    "currentItemFontFamily": 5,
    "currentItemFontSize": 20,
    "currentItemTextAlign": "left",
    "currentItemStartArrowhead": null,
    "currentItemEndArrowhead": "arrow",
    "currentItemArrowType": "round",
    "currentItemFrameRole": null,
    "scrollX": 400,
    "scrollY": 400,
    "zoom": { "value": 0.85 },
    "currentItemRoundness": "round",
    "gridSize": 20,
    "gridStep": 5,
    "gridModeEnabled": false,
    "gridColor": {
      "Bold": "rgba(217, 217, 217, 0.5)",
      "Regular": "rgba(230, 230, 230, 0.5)"
    },
    "currentStrokeOptions": null,
    "frameRendering": {
      "enabled": true,
      "clip": true,
      "name": true,
      "outline": true,
      "markerName": true,
      "markerEnabled": true
    },
    "objectsSnapModeEnabled": false,
    "activeTool": {
      "type": "selection",
      "customType": null,
      "locked": false,
      "fromSelection": false,
      "lastActiveTool": null
    },
    "disableContextMenu": false
  },
  "files": {}
}
```

## Design System

### Color Palette

**Primary colors:**
| Role | Color | Usage |
|------|-------|-------|
| Stroke default | `#1e1e1e` | Most borders and lines |
| Stroke alt | `#000000` | Legacy/alternate black |
| Background white | `#ffffff` or `#fff` | White fill containers |
| Transparent | `transparent` | No fill (most common) |

**Semantic colors:**
| Role | Background | Stroke/Text |
|------|-----------|-------------|
| Highlight/Warning | `#ffec99` (yellow) | `#d9480f` (orange) |
| Success/Databricks | `#b8d432` (lime) | `#12b886` (green) |
| Error/Alert | `#ffc9c9` (light red) | `#e03131` (red) |
| Info/Link | `#a5d8ff` (light blue) | `#228be6` (blue) |
| Streaming/Real-time | `#51e7ff` (cyan) | `#00add4` or `#9cebff` |
| Orange accent | `#e8590c` | `#f08c00` |
| Purple accent | `#744fb5` | `#0a11d3` |
| Neutral light | `#e9ecef`, `#ced4da` | `#495057`, `#343a40` |
| Neutral bg | `#f1f1f1` | — |
| Gold | `#ddb60c` | `#e89f01` |

### Typography

| Level | fontFamily | fontSize | strokeColor | Usage |
|-------|-----------|----------|-------------|-------|
| Main Title | 5 (Excalifont) | 80-90 | `#1e1e1e` | Top of diagram |
| Section Heading | 5 (Excalifont) | 36-48 | `#1e1e1e` or `#d9480f` | Section labels |
| Subsection | 1 (Virgil) | 28-32 | `#1e1e1e` | Block titles |
| Body text | 1 (Virgil) | 20 | `#1e1e1e` | Descriptions |
| Small label | 1 (Virgil) | 16-18 | `#1e1e1e` or `#495057` | Annotations |
| Code/tech | 3 (Cascadia) | 18-20 | `#0a11d3` or `#d9480f` | Code snippets, API names |

- `fontFamily: 1` = Virgil (hand-drawn) — most common for body
- `fontFamily: 3` = Cascadia (monospace) — for code
- `fontFamily: 5` = Excalifont — for titles and headings
- `textAlign`: "center" for labels inside shapes, "left" for standalone text
- `verticalAlign`: "top" for standalone, "middle" for text inside containers
- `lineHeight`: always 1.25

### Shapes

**Rectangles (containers):**
- `roundness: { "type": 3 }` — standard rounded corners
- `strokeWidth: 2` (default), `4` for emphasis
- `fillStyle: "solid"` (most common), "hachure" for sketchy effect
- `roughness: 1` (sketchy look — most common)
- `opacity: 100`

**Ellipses (decorative/grouping):**
- `roundness: null` (ellipses don't use roundness)
- Often used as large background grouping shapes
- Common bg colors: `#e9ecef`, `#ced4da`

**Arrows:**
- `endArrowhead: "arrow"` (always)
- `startArrowhead: null` (always)
- `strokeWidth: 2` (standard flow), `4` (emphasis)
- `strokeStyle: "solid"` (most), "dashed" for optional/async flows
- `roughness: 1`
- `roundness: null`
- Points array with 2-3 points for simple connections
- Use `startBinding` and `endBinding` to connect to elements when possible

### Element Template

Every element MUST have these fields:

```json
{
  "id": "<unique-id>",
  "type": "<rectangle|text|arrow|ellipse|line|diamond>",
  "x": 0,
  "y": 0,
  "width": 200,
  "height": 50,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 1,
  "strokeStyle": "solid",
  "roughness": 1,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "index": "<fractional-index>",
  "roundness": null,
  "seed": <random-integer>,
  "version": 1,
  "versionNonce": <random-integer>,
  "isDeleted": false,
  "boundElements": [],
  "updated": 1770570570816,
  "link": null,
  "locked": false
}
```

**Additional fields by type:**

Text elements add:
```json
{
  "text": "Content here",
  "fontSize": 20,
  "fontFamily": 1,
  "textAlign": "left",
  "verticalAlign": "top",
  "containerId": null,
  "originalText": "Content here",
  "autoResize": true,
  "lineHeight": 1.25,
  "rawText": ""
}
```

Rectangle/Ellipse elements add:
```json
{
  "hasTextLink": false
}
```

Arrow elements add:
```json
{
  "startBinding": null,
  "endBinding": null,
  "lastCommittedPoint": null,
  "startArrowhead": null,
  "endArrowhead": "arrow",
  "points": [[0, 0], [100, 0]],
  "hasTextLink": false,
  "moveMidPointsWithElement": false
}
```

## ID Generation

Generate unique IDs using random alphanumeric strings of 8-21 characters. Example patterns from existing files:
- `"5Kaw90-xM5_wjxs_AMjjo"` (21 chars with hyphens/underscores)
- `"ys3yGRn5"` (8 chars)
- `"tCUXIeRL71fMiGLLoJILa"` (21 chars)

Use a mix of lengths. Each ID must be unique within the file.

## Fractional Index

The `index` field uses fractional indexing for element ordering. Use simple alphabetical sequences:
- Start with `"a0"`, `"a1"`, `"a2"`, etc.
- Or use `"b0"`, `"b1"`, `"b2"` for later elements
- These determine rendering order (back to front)

## Seed Generation

`seed` and `versionNonce` must be random positive integers. Use different values for each element. Range: 1 to 2147483647.

## Layout Guidelines

### Overall Structure (top to bottom):
1. **Title** — large text (fontFamily=5, ~80-90px) at the very top
2. **Subtitle/Description** — optional, fontFamily=1, ~28-36px below title
3. **Main content area** — flows left-to-right or top-to-bottom
4. **Legend/Notes** — bottom or right side

### Spacing:
- Title to first content: ~100-150px vertical gap
- Between major sections: ~80-100px
- Between elements within a section: ~40-60px
- Padding inside containers: ~20-30px
- Standard block width: 200-400px
- Standard block height: 60-120px

### Common Patterns:
- **Flow diagram**: Rectangles connected by arrows left-to-right
- **Architecture diagram**: Stacked layers with labeled sections
- **Pipeline**: Sequential blocks with arrows showing data flow
- **Comparison**: Side-by-side rectangles with labels

### Content Planning:
Based on the topic, create a diagram with:
- 1 main title
- 3-6 major sections/blocks
- Arrows showing relationships/flows
- Color coding using the semantic palette above
- Brief text labels (not paragraphs)

## Important Rules

1. The output MUST be valid JSON — no trailing commas, no comments
2. Every element needs a unique `id` and unique `seed`/`versionNonce`
3. Text `width` should approximate: `fontSize * 0.6 * text.length` (rough estimate)
4. Text `height` should approximate: `fontSize * lineHeight`
5. Use `containerId` on text elements to bind them inside a rectangle (the rectangle needs `boundElements: [{"id": "<text-id>", "type": "text"}]`)
6. Arrow `points` are relative to the arrow's x,y position
7. Keep the diagram focused — prefer clarity over complexity
8. Use color semantically — green for success/good, red for errors, yellow for highlights, blue for info
9. Total elements should be between 15-60 for a clean diagram
10. The `updated` timestamp can be a fixed value like `1770570570816`

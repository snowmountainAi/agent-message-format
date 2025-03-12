# Agent Message Format (AMF)

AMF is an open standard of markdown with a set of custom elements for common elements to standardize the messages used by AI assistants.

## Rationale

At Snowmountain AI, we wanted to create a universal format that can be used easily for reading and writing by humans, programs and language models. Compared to plain markdown, this would enable better information hierarchy and legibility and present information in multiple formats: Chat messages, documents, slideshows and responsive webpages.

Markdown has already been found inadequate for conversations with AI assistants. While CommonMark or Github-flavored-markdown (GFM) support elements like lists, tables, code blocks and images, AI assistants like ChatGPT or Gemini have found it necessary to extend it for additional abilities.

- Rendered/evaluated code blocks (like mermaid diagrams)
- LaTeX for math
- Citations
- File attachments
- Charts
- Collapsibles
- Popovers
- Cards
- Collection of Cards

The idea is to achive better visual presentation while retaining semantic information for easy parsing by humans, programs and LLMs. This requires achieving the right balance between plain markdown and full HTML.

## Approach

We take Github-flavored-markdown as a starting point because it already supports mermaid diagrams and LaTeX for math.

We define the DSL for other custom elements.

## Examples


### File attachment

```
<amf-attachment url="" type="" size="" name=""></amf-attachment>
```

### Diagrams

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

### Math

Example of inline math $x = 1$

$$
y = x + 3
$$

### Citations

```
<amf-citation type="inline"></amf-citation
<amf-citation type="full" /></amf-citation
```

### Collapsible

<details>
    <summary>Heading</summary>
    More text goes here
</details>

### Charts

```
<amf-pie-chart></amf-pie-chart>
<amf-bar-chart></amf-bar-chart>
```
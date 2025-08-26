# AI Presentation Generator: Technical Implementation Overview

## Input Text Processing and Slide Mapping

The application employs a sophisticated multi-stage approach to transform raw text into structured presentation content. The process begins with intelligent content analysis through Large Language Model (LLM) integration, supporting OpenAI, Anthropic, and Google providers. 

The system creates a detailed analysis prompt that instructs the AI to examine the input text and optional guidance parameters (such as "investor pitch deck" or "technical training"). The LLM analyzes content density, identifies key themes, and determines optimal slide count (typically 5-12 slides) based on the material's complexity and scope.

Each slide undergoes structured mapping where the AI identifies appropriate titles (maximum 10 words), extracts 2-5 key content points, and determines slide types (title, content, summary). The system validates the AI response through JSON parsing, ensuring proper structure with required fields including slide titles, content arrays, presentation metadata, and optional speaker notes.

## Template Style and Asset Application

The visual styling system implements a comprehensive template analysis pipeline that extracts design elements from uploaded PowerPoint files (.pptx/.potx). The application uses JSZip and PizZip libraries to decompress and parse the template's XML structure.

The template extraction process reads multiple XML files within the PowerPoint archive: `theme1.xml` for color schemes and font definitions, `slideMaster1.xml` for layout structures, and individual slide XML files for placeholder positioning. The system extracts critical styling information including accent colors, text colors, font families, background settings, and spatial positioning data.

For style application, the system converts extracted EMU (English Metric Units) positioning data to inches for precise element placement. Color values are parsed from hexadecimal format and applied consistently across generated slides. Font information, including typeface and sizing, is preserved from the template's typography settings.

The implementation creates new slides using PptxGenJS while applying extracted template characteristics. This approach ensures brand consistency by reusing the template's visual identity while populating it with AI-generated content, resulting in professional presentations that maintain the original design aesthetic.

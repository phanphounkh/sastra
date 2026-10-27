# Khmer OCR

OCR converts photographed or scanned documents into usable Unicode text. In SASTRA AI, approved OCR output should flow directly into chat and RAG.

## Target workflow

1. Upload an image or scanned PDF.
2. Validate its type, size, and page count.
3. Detect text regions and reading order.
4. Extract and normalize Khmer Unicode text.
5. Show confidence and source-page information.
6. Let the user review and correct the result.
7. Send approved text to chat or index it for RAG.

## Khmer-specific requirements

- Support common Khmer fonts and historical document layouts.
- Handle low-resolution scans, skew, blur, shadows, and phone photographs.
- Normalize equivalent Khmer Unicode sequences without changing meaning.
- Preserve paragraphs, tables, headings, and page references where possible.
- Test mixed Khmer/Latin text, numbers, dates, and proper names.

English, French, and Chinese OCR should be available when supported by the selected provider.

## Evaluation

Measure character error rate, word error rate, layout preservation, latency, and cost across document types and scan quality.

Track the dedicated roadmap in [issue #5](https://github.com/phanphoun123-lab/sastra/issues/5).


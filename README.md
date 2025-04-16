# HTTPx Visualizer

A browser-based, single-file tool to visually parse, filter, sort, and explore HTTPx JSON output. This enhanced version provides a more refined UI and advanced features for efficient analysis of web scan results.

> [!NOTE]
> MADE BY : Claude 3.7 Sonnet (Thinking) and enhanced by Gemini 2.5 pro 😝

---

## Features

- **Modern UI/UX:** Clean, responsive interface built with vanilla HTML, CSS, and JavaScript.
- **Drag & Drop Upload:** Easily load your HTTPx JSON files.
- **Statistical Overview:** Quickly grasp key metrics (total domains, endpoints, status code counts).
- **Advanced Filtering:**
  - Filter by Domain, Status Code (ranges like 2xx, 3xx), Web Server, Content Type, and Page Title.
  - **Multi-Select Technology Filter:** Filter results based on detected technologies using a searchable dropdown and visual pills.
- **Interactive Results Table:**
  - **Sortable Columns:** Sort data by Domain, URL, Status Code, Title, Web Server, Content Type, Technology Count, and Response Time.
  - **Pagination:** Handles large datasets efficiently with navigation controls.
  - **Detailed View:** Expand rows to see all fields from the JSON data, including request/response details and a response body preview.
  - **Tech Tags:** See detected technologies directly in the table.
  - **Clear Status Indicators:** Color-coded status code pills.
- **CSV Export:** Export the currently _visible_ filtered and sorted data to a CSV file.
- **Standalone:** Runs entirely in the browser – no server-side components needed. Just a single HTML file.

## How to Use

1. **Get the File:** Download the `httpx-visualizer.html` file from this repository.
2. **Open in Browser:** Open the downloaded HTML file in your web browser (Firefox, Chrome, Edge, etc.).
3. **Upload Data:**
   - Run your `httpx` scan with the `-json` flag:

```bash
cat input.txt | httpx -nc -silent -random-agent -probe -cdn -asn -extract-fqdn -cname -ip -td -server -favicon -j > results.json
```

- Drag and drop the generated `results.json` file onto the upload area in the visualizer, or click the area to browse and select the file.

4. **Explore:** The visualizer will process the file and display the results. Use the filters, sorting, pagination, and expandable rows to analyze your data.

## Input Format

This tool requires JSON output generated by the [HTTPx tool](https://github.com/projectdiscovery/httpx) using the `-json` flag. Ensure your `httpx` command includes flags for the data you want to visualize (e.g., `-tech-detect`, `-title`, `-status-code`, etc.).

Example `httpx` command:

```bash
cat input.txt | httpx -nc -silent -random-agent -probe -cdn -asn -extract-fqdn -cname -ip -td -server -favicon -j > results.json
```

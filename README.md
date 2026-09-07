# Initial Roadmap
	🟡 Clean and structure original data from http://www.wildsingapore.com
		🟡 Entries	
			 ✅ Image galleries
			 ✅ Text sections
			 ✅ Links & References
			 ✅ Location information
			 🟡 IUCN & RDB status
			 ✅ Atomic entry content
			 🔲 Higher rank entries content
			 ✅ (Dev) Sidebar section navigation (collapsible on mobile view)
			 ✅ Assigning zones to entries
			 ✅ Assigning habitats to entries
	   🔲 Entry guides (/wildfacts/guides)
			 🔲 Pages to aggregate guides
			 🔲 Entry guide content (pages on how to tell apart things)
	🟡 Entry aggregates
		🟡 Explore page
			✅ Text query search
			✅ Pagination
			🟡 Taxa filter
				✅ Logic for single checkbox single taxa
				✅ Logic for single checkbox multiple taxa
				🔲 Logic for "Other" checkbox option
		🟡 Step-by-step Photo indexes
			🟡 Identify features to group entries by
            ✅ Marine
            🔲 Terrestrial
            🔲 Freshwater
         🔲 Add graphics for every button
         🔲 Add photoindexes that group animals by their features
            🔲 Adapt from original fi.htm pages
            🔲 Create new photoindexes
            🔲 Assign features to photoindexes
    🔲 New pages that reflect the goals of the new site
      🔲 Make a Difference pages
         🟡 For Individuals
            🟡 Index page
            🟡 Nature Communities & Groups aggregate
               🔲 Nature Communities & Groups pages
         🟡 For Teachers
         🔲 For guides
      🔲 Our wild spaces (a page for every place)
      🔲 Habitat pages
    🔲 Add a search engine in the "For Teachers" page
    🔲 Add classroom activities with proper YAML headers
    🔲 Vector art and background illustrations 
---

# Wild Singapore

The Wild Singapore website is a guide to the flora and fauna of Singapore's intertidal shores.

**Original Site:** [wildsingapore.com](http://www.wildsingapore.com)

---

## Table of Contents

- [About the Project](#about-the-project)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [Submission Guidelines](#submission-guidelines)
- [License & Attribution](#license--attribution)

---

## About the Project

Wild Singapore is an open, crowdsourced encyclopedia of Singapore's coastal and intertidal biodiversity. The site features:

- **Detailed species factsheets** with photos and identification features
- **Field guides** organized by taxonomy
- **Interactive photo galleries** for easy exploration
- **Information organized by location and ecosystem type**

The project is organized taxonomically (ascidians, mollusks, crustaceans, etc.) and includes both animals and plants found on Singapore's shores. All content is freely available for educational use.

---

## Project Structure

```
wild-singapore.github.io/
├── _config.yml              # Jekyll site configuration
├── _data/                   # YAML data files (navigation, attributes, etc.)
├── _includes/               # HTML/Liquid components (buttons, grids, sidebars)
├── _layouts/                # Page templates (default, home, page)
├── assets/                  # CSS stylesheets and images
├── entries/                 # Species factsheets organized by taxonomy
│   ├── ascidiacea/         # Sea squirts
│   ├── bryozoa/            # Bryozoans
│   ├── cnidaria/           # Corals, sea anemones, jellyfish
│   ├── crustacea/          # Crustaceans
│   ├── ctenophora/         # Comb jellies
│   ├── echinodermata/      # Sea stars, sea cucumbers
│   ├── insecta/            # Insects
│   ├── mollusca/           # Mollusks
│   ├── porifera/           # Sponges
│   ├── vertebrates/        # Fish and vertebrates
│   ├── worm/               # Marine worms
│   ├── arachnida/          # Arachnids
│   └── plants/             # Marine plants
├── wildfacts/               # Additional taxonomic and reference guides
├── _site/                   # Generated site (do not edit)
└── index.md                 # Home page
```

---

## Getting Started

### Prerequisites

- **Ruby** (version 2.7 or higher)
- **Bundler** (install with `gem install bundler`)
- **Jekyll** (install with `gem install jekyll`)
- **Git**

### Local Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Wild-Singapore/wild-singapore.github.io.git
   cd wild-singapore.github.io
   ```

2. **Install dependencies:**
   ```bash
   bundle install
   ```
   This will install every gem listed within the Gemfile.

3. **Start the development server:**
   ```bash
   bundle exec jekyll serve --livereload
   ```
   The site will be available at `http://localhost:4000`
   Add the `--trace` command if you need to debug anything.

4. **Make your changes** in the `entries/`, `wildfacts/`, or other content directories.

5. **See changes live** — Jekyll will automatically rebuild as you save files.

---

## Contributing

### Types of Contributions

We welcome all kinds of contributions:

- **Add new species factsheets** with identification features and photos
- **Add or improve photos** to existing entries
- **Fix typos and errors** in existing content
- **Add missing taxonomic information** or cross-references
- **Improve layout and navigation** features
- **Create new guides or reference materials**

### How to Contribute

1. **Fork the repository** on GitHub
2. **Create a new branch** for your changes:
   ```bash
   git checkout -b add-species-name
   ```
3. **Make your edits** (see [Submission Guidelines](#submission-guidelines))
4. **Test locally** with `bundle exec jekyll serve`
5. **Commit with clear messages:**
   ```bash
   git commit -m "Add blob ascidian factsheet"
   ```
6. **Push to your fork:**
   ```bash
   git push origin add-species-name
   ```
7. **Create a Pull Request** on GitHub with a description of your changes

---

## Submission Guidelines

### Adding a New Species Factsheet

1. **Create a new Markdown file** in the appropriate `entries/` subdirectory:
   - Example: `entries/ascidiacea/myspecies.md`
   - Use lowercase filenames with hyphens for multi-word names

2. **End goal of entry metadata (subject to change):
   ```yaml
   ---
   title: "Common name (Scientific name) "
   description: "Fact sheet with photos on flora and fauna of Singapore's intertidal shores"
   keywords: "common-name, scientific-name, taxonomy, field, guide, seashore, singapore, facts"
   layout: default
   attributes: [1,2,3 ...]
   zone: terrestrial|intertidal
   englishname: ""
   malayname: ""
   kindgom: ""
   phylum: ""
   class: ""
   order: ""
   family: ""
   genus: ""
   species: ""
   ---
   ```

3. **Structure your content** following this template:
   ```markdown
   # [Category name]
   [Navigation links to related pages]
   
   **Phylum/Kingdom** | **Class/Subphylum** | **Other taxonomy**
   
   ## Common Name
   *Scientific name* | *[status/notes]*
   
   ---
   
   ### Where seen?
   Description of habitats and locations where found.
   
   ### Features
   Key identification characteristics.
   
   ### Behavior
   (Optional) Behavioral information.
   
   ### Ecological Role
   (Optional) Ecological significance.
   
   [Photo(s) if available]
   ```

4. **Add keywords** for searchability — include common names, scientific names, and taxonomic terms

5. **Include high-quality images** from a cloud service provider, do not commit entry images into the repo

### Editing Existing Content

- Maintain the existing structure and style
- Update the content while preserving the front matter
- Add new information or corrections clearly
- If making substantial changes, update the last-modified note

### Style Guidelines

- Work in progress

---

## License & Attribution

### For Users

The content on this site is freely available for:
- **Educational use** in classroom settings
- **Personal websites** and school projects
- **Non-commercial educational activities**


### Contributor License

By contributing to this repository, you agree that your contributions can be used and distributed under the same terms as the existing content, with appropriate attribution.

---


## Community & Support

- **Report issues or suggest features:** Open an issue on GitHub
- **Ask questions:** Comment on relevant issues or pull requests

---

## Credits

- **Original Creator:** Ria Tan 
---

## Additional Resources

- [Jekyll Documentation](https://jekyllrb.com/)
- [Markdown Syntax Guide](https://www.markdownguide.org/)
- [Wild Singapore Main Site](http://www.wildsingapore.com)

---

## Future Direction

We might integrate other taxa into the website. So the Photo Index and general organisation of entries and aggregates have to be heavily edited. Thus we have the need to make everything as modular as possible.

---

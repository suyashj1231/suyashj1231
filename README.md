<h1 align="center">Suyash Jain</h1>

<p align="center">
  <strong>M.S. Computer Science @ UC Irvine</strong> · Systems · Search &amp; Retrieval · Applied ML
</p>

<p align="center">
  <a href="mailto:j.suyash1231@gmail.com">Email</a> ·
  <a href="https://www.linkedin.com/in/jain-suyash">LinkedIn</a> ·
  <a href="https://suyashjain.app/">Portfolio</a>
</p>


## About me

- M.S. in Computer Science at UC Irvine (expected June 2028). B.S. from UCI in Computer Science and Business Information Management, double major, GPA 3.75 (June 2026).
- I like performance work I can measure, and I usually end up writing the benchmark harness myself: latency histograms for a matching engine, frame timing for a GPU terminal.
- Open-source contributor to [Apache Texera](https://github.com/apache/texera), the collaborative data-science platform that started at UCI.
- I'm looking for software engineering roles, both new-grad full-time and Summer 2027 internships.


## Featured projects

### [Limit Order Book & Matching Engine](https://github.com/suyashj1231/lob-latency-study) · C++
Rebuilt a price-time-priority order book from a `std::map` + list baseline into a flat, tick-indexed, pool-allocated structure with no heap allocation on the hot path. Per-operation latency dropped 4.5-9.2x (cancel went from 294 ns to 32 ns on a 1M-order book). I wrote the measurement harness too: a cycle-clock histogram for p50-p99.99, a NASDAQ ITCH 5.0 decoder with book-delta replay, and a core-pinned runner instrumented with `perf`.

### [turbo-rag](https://github.com/suyashj1231/turbo-rag) · Python, FastAPI
Question answering over 7,000 book descriptions, written without LangChain or LlamaIndex. Retrieval fuses a hand-written BM25 index with dense MiniLM vectors (reciprocal rank fusion), then reranks with Cohere or a local cross-encoder. Every sentence of an answer must cite a source; a validator retries once and otherwise answers "I don't know". It keeps multi-turn sessions, runs as a FastAPI service structured like a Lambda handler, and CI blocks any PR that drops retrieval metrics or Ragas faithfulness, relevancy and context precision.

### [Web Search Engine](https://github.com/suyashj1231/inelastic-search-engine) · Python
Search engine written from scratch over UCI's ICS web crawl, with no search library. It cleans HTML down to visible text, builds a Porter-stemmed inverted index that boosts title and heading matches, intersects postings smallest-first for Boolean queries, and ranks by TF-IDF blended with PageRank. An optional BART-Large-CNN step writes two-sentence result summaries.

### [GPU-Accelerated Terminal Emulator](https://github.com/suyashj1231/OpenGL) · C++, OpenGL
A terminal whose batch renderer and dynamic texture atlas draw 10,000+ characters in one draw call: 460 FPS, 2 ms frames, and more than 80% of the CPU left free. It runs on a POSIX PTY and prints 700K+ line outputs 50% faster than a CPU-rendered terminal.

### [Stowly](https://github.com/suyashj1231/stowly) · Swift, SwiftUI
macOS menu-bar app that turns saved Instagram, TikTok, YouTube, LinkedIn and X posts into categorized task cards. Its LLM provider layer falls back from Gemini to a fully local Ollama + Whisper pipeline, and an iPhone-to-Mac relay runs over ntfy.sh. Covered by 123 tests.

### [CypherSort](https://github.com/suyashj1231/cyphersort) · Python, PyQt6, Ollama
Watches your Downloads folder, reads the content of each new PDF, image, text file or .docx with a local Ollama model, and files it into a Cryptomator-encrypted vault, creating folders as it goes (every ICS 53 lecture lands in `courses/ics53/`). A review queue shows the suggested folder and the model's reason before anything moves, and every move is logged. It runs fully offline.

### [CipherSort for macOS](https://github.com/suyashj1231/CipherSort) · Swift, SwiftUI
A native rewrite of CypherSort that classifies new files using only Apple's on-device frameworks: FSEvents for watching, Vision OCR and PDFKit for text, and NaturalLanguage sentence embeddings blended with metadata, with confidence weighted by text quality. It benchmarks itself on a sample of the RVL-CDIP document dataset.

### [VLM Image Attacks Under Deployment Conditions](https://github.com/suyashj1231/vlm-image-attack-transfer) · Python, PyTorch, MLX
Two published papers seem to disagree on whether adversarial images transfer across vision-language models. Over 11 experiments spanning 3 model scales, 6 quantization levels and 11 preprocessing pipelines, this study shows that they measure different things: taking *control* of a model (about 0% transfer to an unseen architecture) versus the target text simply being *readable* in the image (40-100%). It also finds that quantization is not a defense, while downscaling to 256 px is. The only string any attack tries to force is a harmless placeholder.


## More projects

| Project | What it is | Stack |
|---|---|---|
| [BusTrack](https://github.com/suyashj1231/bustrack) | iOS tracker for UCI's Anteater Express: live map, favorite stops, bus-is-close alerts, home and lock screen widgets | Swift, SwiftUI, WidgetKit |
| [Larya](https://larya.vercel.app) | Full-stack storefront for a streetwear brand, with accounts, basket, wishlist and an admin console (live site) | Next.js, TypeScript, Supabase |
| [Eco Flight Finder](https://github.com/suyashj1231/eco-flight-finder) | Flight search ranked by an eco-score that combines carbon emissions and duration | FastAPI, SQLAlchemy, JavaScript |
| [Doomscroll Detector](https://github.com/suyashj1231/Doomscroll_detector) | Real-time on-device vision that flags phone use and gaze distraction | Python, YOLOv8, MediaPipe, OpenCV |
| [claude-usage-bar](https://github.com/suyashj1231/claude-usage-bar) | Dependency-free statusline showing Claude Code plan usage live, synced across terminals | Bash |
| [Airport Database](https://github.com/suyashj1231/airport-db-gui) | Normalized SQLite airport database with enforced foreign keys and an event-driven Tkinter GUI | Python, SQLite |


## Open source

**[Apache Texera](https://github.com/apache/texera)** · Scala, Java · merged PRs:
- [Remove null padding in reservoir sampling](https://github.com/apache/texera/pull/5606): a data-integrity fix for empty records under uneven worker loads
- [Apply LakeFS error handling to all call sites](https://github.com/apache/texera/pull/5607): clear errors and correct HTTP status codes in the file service
- [Honor the File Scan Encoding field](https://github.com/apache/texera/pull/8605)
- [Test coverage for `ValidationWorkflowService.combineValidation`](https://github.com/apache/texera/pull/8604)


## Experience

- **Student Desktop Analyst, UCI Office of Information Technology** (Dec 2024 - Jun 2026)<br>
  Built an internal support chatbot on a fine-tuned ZotGPT pipeline. Migrated campus IT services from Azure to AWS with no downtime for 3,000+ users, and cut deployment time 40% with GitHub Actions provisioning.
- **Technical Director, UCI Engineering Student Council** (Jan 2024 - Jun 2026)<br>
  Moved the council's web presence onto one React + Google Cloud platform, which cut feature deploys from 1-2 days to minutes. Built a Flask QR-code attendance system with role-based access control.
- **Software Developer, Google Developer Student Club** (Jan - Mar 2024)<br>
  Built a React Native + Firebase civic reporting app that cut issue resolution time 40%.
- **Software Engineering Intern, IIITDM Jabalpur** (Apr - Jun 2023)<br>
  Wrote embedded control firmware for a SERB/DST-funded 3D-printing positioning system.


## Tech

**Languages:** Python · C/C++ · Java · JavaScript/TypeScript · Swift · Go · Rust · SQL<br>
**ML:** PyTorch · Hugging Face · scikit-learn · LangChain · OpenCV · YOLOv8<br>
**Infra & cloud:** AWS (Lambda, S3, EC2, DynamoDB) · Google Cloud · Docker · Kubernetes · gRPC · GitHub Actions<br>
**Web & data:** React · Next.js · Node.js · FastAPI · Flask · PostgreSQL · SQLite · Supabase


<p align="center">
  <img
    src="https://github-readme-stats-xi-liart.vercel.app/api?username=suyashj1231&show_icons=true&include_all_commits=true&count_private=true&theme=transparent&rank_icon=github&bg_color=00000000&title_color=58a6ff&text_color=c9d1d9&icon_color=58a6ff&border_color=30363d&hide=contribs"
    width="49%"
    alt="Suyash's GitHub stats"
    height="180"
  />
  <img
    src="https://github-readme-stats-xi-liart.vercel.app/api/top-langs/?username=suyashj1231&layout=compact&theme=transparent&hide_border=true&langs_count=8&bg_color=00000000&title_color=58a6ff&text_color=c9d1d9&hide=jupyter%20notebook,html,css,tex"
    width="49%"
    alt="Top languages"
    height="180"
  />
</p>

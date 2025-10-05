# 📝 Google Docs LLD (C++ Implementation)

> A detailed **Low-Level Design (LLD)** and **C++ implementation** of a simplified **Google Docs–like document editor**, following a modular, extensible, and object-oriented design.

---

## 📘 Overview

This project demonstrates a **Google Docs-inspired system** in **C++**, focusing on:

- Modular **Document, Editor, and Client** architecture.
- **Persistence abstraction** for saving to different backends.
- **Document elements abstraction** to support text, images, or future elements.
- Clean **OOP design** suitable for **system design interviews** or portfolio demonstration.

---

## 🧩 UML Design

The design follows your uploaded diagram:

- **Document**: Manages a collection of **DocumentElements** (Text, Image, etc.)
- **DocumentElement**: Abstract base for any content element with a `render()` method.
- **DocumentEditor**: Provides editing APIs like `addText()` and `addImage()`, interacts with persistence layer.
- **Persistence**: Abstract save interface, implemented by `FileStorage` and `DBStorage`.
- **Client**: Uses `DocumentEditor` and `DocumentRender` to interact with the document.
- **DocumentRender**: Handles rendering a document visually.

🔗 **[View editable UML diagram on Excalidraw](https://excalidraw.com/#json=CNpVaVQ8HUH909GXtlHO0,OZyZXwBIp15VRAr5pH26nw)**  

---

## 🧱 Core Components

| Component | Description |
|------------|--------------|
| **DocumentElement (Abstract)** | Base class for all elements in the document. Must implement `render()`. |
| **TextElement / ImageElement** | Concrete elements for text and images, derived from `DocumentElement`. |
| **Document** | Maintains a collection of elements; provides APIs `addElement()`, `getElement()`, `elements()`. |
| **DocumentRender** | Responsible for rendering the document (`render()`) by iterating elements. |
| **DocumentEditor** | Provides APIs to modify the document: `addText()`, `addImage()`. Uses `Persistence` for storage. |
| **Persistence (Abstract)** | Interface for saving data. Can be implemented as `FileStorage` or `DBStorage`. |
| **FileStorage / DBStorage** | Concrete persistence classes implementing `save(String)`. |
| **Client** | Uses `DocumentEditor` and `DocumentRender` to create, edit, and render documents. |

---

## 🏗️ Design Principles

- **Abstraction & Polymorphism**
  - `DocumentElement` and `Persistence` allow extension without modifying existing code.
- **Single Responsibility**
  - Each class handles one concern: editing, rendering, storage.
- **Open/Closed Principle**
  - New elements or storage backends can be added without changing existing code.
- **Separation of Concerns**
  - Client interacts only with Editor and Renderer; persistence is decoupled.

---

##🧑‍💻 Author

Durgesh Singh
🎓 M.Tech CSE @ NIT Jalandhar
🏅 GATE CSE Qualified | Software Engineer | System Design Enthusiast
🔗 LinkedIn
 | ✉️ durgeshkumar0187@gmail.com

📜 License

MIT License — Free to use and modify with attribution.


---

If you want, I can also **draw a sequence diagram and workflow description** based on this diagram, so the README becomes **fully professional for GitHub portfolio**.  

Do you want me to do that next?


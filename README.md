# Getting Started with GitHub Copilot

<img src="https://octodex.github.com/images/Professortocat_v2.png" align="right" height="200px" />

Hey MS-stev-van!

Mona here. I'm done preparing your exercise. Hope you enjoy! 💚

Remember, it's self-paced so feel free to take a break! ☕️

[![](https://img.shields.io/badge/Go%20to%20Exercise-%E2%86%92-1f883d?style=for-the-badge&logo=github&labelColor=197935)](https://github.com/MS-stev-van/skills-getting-started-with-github-copilot/issues/1)

## Application architecture

```mermaid
flowchart LR
    U[User in Browser]

    subgraph Frontend["Static Frontend — src/static"]
        HTML[index.html]
        JS[app.js]
        CSS[styles.css]
    end

    subgraph Backend["FastAPI Backend — src/app.py"]
        ROOT["GET /"]
        API["GET /activities"]
        SIGNUP["POST /activities/{name}/signup"]
        DATA[("In-memory Activities<br/>Python Dictionary")]
    end

    U -->|Open application| ROOT
    ROOT -->|Redirect| HTML
    HTML --> JS
    HTML --> CSS
    JS -->|Fetch activities| API
    API --> DATA
    DATA -->|Activity data| API
    API -->|JSON response| JS
    JS -->|Submit student email| SIGNUP
    SIGNUP -->|Validate and append participant| DATA
    SIGNUP -->|Confirmation or error| JS
    JS -->|Update activity UI| U
```

The browser loads a plain HTML, CSS, and JavaScript interface. The JavaScript calls the FastAPI endpoints, which read or update an in-memory Python dictionary. Restarting the server resets all signup data.

---

&copy; 2025 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

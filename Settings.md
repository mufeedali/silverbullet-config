---
tags:
- meta
- space-config
---

This is where you configure SilverBullet to your liking. See [[^Library/Std/Config]] for a full list of configuration options.

```space-lua
config.set {
  plugs = {
    -- Add your plugs here (https://silverbullet.md/Plugs)
    -- Then run the `Plugs: Update` command to update them
    "github:joekrill/silverbullet-treeview/treeview.plug.js",
    "ghr:MrMugame/silversearch",
    "github:justyns/silverbullet-ai/silverbullet-ai.plug.js",
    "github:silverbulletmd/silverbullet-mermaid/mermaid.plug.js",
    "github:jim-fx/silverbullet-excalidraw/excalidraw.plug.js"
  },
  indexPage = "Home",
  actionButtons = {
    {
      icon = "file",
      description = "Quick Note",
      run = function()
        editor.invokeCommand("Quick Note")
      end
    },
    {
      icon = "home",
      description = "Go to the Homepage",
      run = function()
        editor.invokeCommand("Navigate: Home")
      end
    },
    {
      icon = "search",
      description = "Search",
      run = function()
        editor.invokeCommand("Silversearch: Search")
      end
    },
    {
      icon = "book",
      description = "Open page",
      run = function()
        editor.invokeCommand("Navigate: Page Picker")
      end
    },
    {
      icon = "terminal",
      description = "Run command",
      run = function()
        editor.invokeCommand("Open Command Palette")
      end
    },
    {
      icon = "sidebar",
      description = "Toggle Tree View",
      run = function()
        editor.invokeCommand("Tree View: Toggle")
      end
    },
    {
      icon = "arrow-left",
      description = "Go to the previous page",
      mobile = true,
      run = function()
        editor.invokeCommand("Navigate: Back in History")
      end
    }
  },
  treeview = {
    size = 0.5,
    exclusions = {
      {
        type = "tags",
        tags = { "meta" }
      },
      {
        type = "regex",
        rule = "Library"
      }
    },
    dragAndDrop = {
      enabled = true
    }
  },
  hideSyncButton = false,
  libraries = {
    {
      source = "[[!silverbullet.md/Library/Core/*]]"
    }
  },
  ai = {
    textModels = {
      {
        name = "ollama-gemma3",
        modelName = "gemma3:latest",
        provider = "ollama",
        baseUrl = "http://localhost:11434/v1",
        requireAuth = false
      },
      {
        name = "ollama-llama3b",
        modelName = "llama3.2:latest",
        provider = "ollama",
        baseUrl = "http://localhost:11434/v1",
        requireAuth = false
      },
      {
        name = "ollama-qwen",
        modelName = "qwen2.5:latest",
        provider = "ollama",
        baseUrl = "http://localhost:11434/v1",
        requireAuth = false
      }
    }
  }
}
```

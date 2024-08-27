# Generate Cookbook with GPT4

## Code Example


<style>
.code-container {
  position: relative;
  display: block;
  max-width: 100%; /* Ensures the container does not exceed the width of its parent */
}

.copy-btn {
  position: absolute;
  right: 10px;
  top: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  font-size: 12px;
}

.copy-btn:hover {
  background-color: #45a049;
}

pre {
  background: #000; /* Black background */
  color: #fff; /* White text color */
  border: 1px solid #ddd;
  padding: 10px;
  font-size: 14px;
  overflow-x: auto;
  margin: 0; /* Remove default margin */
  max-width: 100%; /* Ensure the pre block does not exceed its parent container */
}

code {
  background: none; /* Remove additional background */
  color: inherit; /* Use inherited text color */
}


</style>

<script>
function copyToClipboard(button) {
  const codeBlock = button.nextElementSibling.querySelector("code");
  const tempTextArea = document.createElement("textarea");
  tempTextArea.value = codeBlock.textContent;
  document.body.appendChild(tempTextArea);
  tempTextArea.select();
  document.execCommand("copy");
  document.body.removeChild(tempTextArea);
  
  // Change button text to show copied status
  button.innerHTML = "Copied!";
  
  // Change button text back to "Copy" after 2 seconds
  setTimeout(() => {
    button.innerHTML = "Copy";
  }, 2000);
}
</script>


<div class="code-container">
  <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>
  <pre><code id="code1">

cookbook

{
  "chapters": [
    {
      "chapter": "Define Game Concept",
      "description": "Establish the core idea and vision for the game.",
      "subItems": [
        {
          "item": "Concept Development",
          "description": "Develop the core idea of the game, including genre, theme, and unique selling points."
        },
        {
          "item": "Initial Research",
          "description": "Research similar games and identify what makes your game unique."
        }
      ]
    },
    {
      "chapter": "Define Target Audience (TA)",
      "description": "Identify and understand your target audience to tailor the game effectively.",
      "subItems": [
        {
          "item": "Audience Research and Personas",
          "description": "Create detailed profiles of your ideal players to guide design decisions."
        }
      ]
    },


our cookbook will convert into workflow graph such

{
    "nodes": [
        {
            "uniq_id": "uniq_id_1",
            "pos_x": -1482.0,
            "pos_y": -1181.0,
            "width": 200.0,
            "height": 200.0,
            "nexts": [
                "uniq_id_2"
            ],
            "type": "START",
            "name": "Node",
            "description": "",
            "tool": "",
            "true_next": null,
            "false_next": null
        },
        {
            "uniq_id": "uniq_id_2",
            "pos_x": -1140.0,
            "pos_y": -898.0,
            "width": 244.0,
            "height": 293.0,
            "nexts": [
                "uniq_id_3"
            ],
            "type": "STEP",
            "name": "Node",
            "description": "write an article, content is startup.md",
            "tool": "",
            "true_next": null,
            "false_next": null
        },
        {
            "uniq_id": "uniq_id_3",
            "pos_x": -717.0,
            "pos_y": -907.0,
            "width": 357.0,
            "height": 306.0,
            "nexts": [],
            "type": "STEP",
            "name": "Node",
            "description": "save the content",
            "tool": "save_file",
            "true_next": null,
            "false_next": null
        },
        {
            "uniq_id": "uniq_id_4",
            "pos_x": -941.0,
            "pos_y": -1334.0,
            "width": 402.0,
            "height": 377.0,
            "nexts": [],
            "type": "TOOL",
            "name": "Node",
            "description": "import os\n\n@tool\ndef save_file(file_path: str, content: str) -> None:\n    \"\"\"\n    :function: save_file\n    :param file_path: Path to the file where the content will be saved\n    :param content: The content to be written to the file\n    :return: True if the file was saved successfully, False otherwise\n    \"\"\"\n    try:\n        with open(file_path, 'w', encoding='utf-8') as file:\n            file.write(content)\n    except Exception as e:\n        print(f\"An error occurred: {e}\")\n",
            "tool": "",
            "true_next": null,
            "false_next": null
        }
    ],
    "node_counter": 5
}


do you understand that we are doing scablility automation generator?
that you will help me gen cookbok and the each subitem in chapter, user will make the content into a prompt. and the final prompt will convert into graph node-edge


so, the core is about write a cookbook which aim to final graph, that is, workflow need spilte into clear, manipulatable node, each chapter, subitem is going to gen one prompt node.

first, give me a cookbook about create a product report that my yotube/podcast content
that is, we need define TA, define what problem to solve, than spilt into chapter, then fill detail as subtitle

second, give me cookbook.json

  </code></pre>
</div>

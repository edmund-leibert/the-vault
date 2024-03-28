---
title: 🗒️ Visual Studio
created: 2023-10-01 14:09
updated: 2023-11-18T02:44
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/🗒️-visual-studio
  - 🔴-academic/📚-educational-resource/format/miscellaneous
  - 🔴-academic/📚-educational-resource/discipline/computer-science/technology/visual-studio
  - 🔴-academic/📚-educational-resource/name/🗒️-visual-studio/🔖-bookmark/🗒️-visual-studio-▹-📋-table-of-contents
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resource🗒️ Visual Studio::🗒️ Visual Studio ▹ 📋 Table of Contents
---

# 🗒️ Visual Studio

---

> [!Abstract]+ Abstract
> 

---

 > [!Info]+ 🕸️ All Mention(s): 
 > 

---

 > [!Info]+ 🔙️ Previous Note(s): 
 > 
 
---

```dataviewjs
// Generate a nested object from a list of file paths
function buildFileTree(files) {
  const root = {};
  
  for (const file of files) {
    let node = root;
    const parts = file.file.path.split('/');
    
    for (const part of parts) {
      if (!node[part]) {
        node[part] = {};
      }
      node = node[part];
    }

    node['metadata'] = file;
  }
  
  return root;
}

// Generate the table of contents recursively from the file tree
function generateTOC(node, indentLevel = 0) {
  let toc = '';
  const indent = ' '.repeat(indentLevel * 2);

  for (const [key, value] of Object.entries(node)) {
    if (key === 'metadata') {
      const file = value;
      toc += `${indent}- ${file.file.link}\n`;
    } else {
      // Check if the current node is a leaf node
      if (value.hasOwnProperty('metadata')) {
        const file = value.metadata;
        toc += `${indent}- ${file.file.link}\n`;
      } else {
        toc += `${indent}- ${key}\n`;
        toc += generateTOC(value, indentLevel + 1);
      }
    }
  }

  return toc;
}


function parseTOC(tocParagraph) {
  // Split the paragraph by lines
  const lines = tocParagraph.split('\n');

  // Initialize an empty list to store the parsed entries
  const parsedList = [];

  // Loop through each line to parse it
  for (const line of lines) {
    // Ignore empty lines
    if (line.trim() === '') continue;

    // Calculate the indent level based on leading spaces (assuming 2 spaces per level)
    const indentLevel = line.search(/\S|$/) / 2;

    // Extract the actual content by trimming the leading spaces
    const content = line.trim();

    // Add the parsed entry to the list
    parsedList.push({
      content: content,
      indentLevel: indentLevel,
    });
  }

  return parsedList;
}

function moveTableOfContentsToTop(inputString) {
    const lines = inputString.trim().split('\n');
    const stack = [];
    let root = [];

    lines.forEach(line => {
        const indent = line.search(/\S|$/);

        while (stack.length > 0 && stack[stack.length - 1].indent >= indent) {
            stack.pop();
        }

        const node = {
            line: line,
            indent: indent,
            children: []
        };

        if (stack.length === 0) {
            root.push(node);
        } else {
            stack[stack.length - 1].children.push(node);
        }

        stack.push(node);
    });

    function sortNodes(nodes) {
        nodes.forEach(node => {
            node.children.sort((a, b) => {
                const hasTableOfContentsA = a.line.includes('📋 Table of Contents');
                const hasTableOfContentsB = b.line.includes('📋 Table of Contents');
                return hasTableOfContentsB - hasTableOfContentsA;
            });

            if (node.children.length > 0) {
                sortNodes(node.children);
            }
        });
    }

    function flattenNodes(nodes, result = []) {
        nodes.forEach(node => {
            result.push(node.line);
            if (node.children.length > 0) {
                flattenNodes(node.children, result);
            }
        });
        return result;
    }

    sortNodes(root);
    return flattenNodes(root).join('\n');
}


function trimTOC(toc, current_path) {
  const lines = toc.split("\n");
  let trimmedTOC = [];

  // Split the current_path into components
  const pathComponents = current_path.split("/");

  // Initialize variables to keep track of the current depth and match
  let currentDepth = -1;
  let currentMatchIndex = 0;
  let shouldStartTrimming = false;

  // Iterate through lines to find matching components
  for (let i = 0; i < lines.length; i++) {
      const line = lines[i];
      
      // Calculate the current line's depth based on the number of leading spaces
      const currentLineDepth = line.match(/^(\s*)/)[0].length;

      if (shouldStartTrimming && currentLineDepth <= currentDepth) {
          // Skip lines that are at a shallower depth than the starting point
          continue;
      }

      // If we find a match for the current path component
      if (line.trim().endsWith(pathComponents[currentMatchIndex])) {
          if (currentMatchIndex < pathComponents.length - 1) {
              // Move to the next path component if there are more
              currentMatchIndex++;
          } else {
              // We've found the line corresponding to the current_path, now start trimming
              currentDepth = currentLineDepth;
              shouldStartTrimming = true;
          }
      }

      if (shouldStartTrimming) {
          // Remove the same number of spaces as the depth of the line where current_path was found
          const adjustedLine = line.slice(currentDepth);
          trimmedTOC.push(adjustedLine);
      }
  }

  return trimmedTOC.join("\n");
}


// Main program
const current_folder = dv.current().file.folder;
console.log(current_folder);
const files = dv.pages(`"${current_folder}"`).values;

// Build file tree
const fileTree = buildFileTree(files);

// Generate Table of Contents
const toc = generateTOC(fileTree);

// Sort Table of Contents
const toc_sorted = moveTableOfContentsToTop(toc);
console.log(toc_sorted);

// trimmedTOC
const trimmed_toc = trimTOC(toc_sorted, current_folder);

dv.paragraph(trimmed_toc);
```


---

> [!Info]+ 🔜 Next Note(s):
> 

---




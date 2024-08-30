---
layout: page/note/basic
---


# Consult 

## 1. Load Template


* Download template
<button class="download-btn" data-url="https://raw.githubusercontent.com/HierarchyChatBot/examples/87119e02fb6a6efa81a1dae4174334fcc74639d1/Uncommon%20Success/consult.json">Download Consult template</button>

* Load Book > consult.json
<img src="./images/button loadbook.webp">

## 2. Chat on chapter

* Choose Chapter, sub item
  * <img src="./images/choose subitem.webp" height="300">
* Chat with AI
  * <img src="./images/chat to AI.webp" height="400">
  * keep chat
  * <img src="./images/chat to AI 2.webp" height="300">

## 3. Fill Answers
<img src="./images/fill to answer.webp" width="400">


## 4. Export Report
* <img src="./images/button export.webp">
* see report
  * <img src="./images/open report.webp.webp">



<script>
    // Select all buttons with the class 'download-btn'
    const downloadButtons = document.querySelectorAll('.download-btn');

    // Add event listeners to each button
    downloadButtons.forEach(button => {
        button.addEventListener('click', function() {
            // Get the URL from the data-url attribute of the clicked button
            const fileUrl = this.getAttribute('data-url');
            
            // Fetch the file and download it
            fetch(fileUrl)
                .then(response => response.blob()) // Convert response to blob
                .then(blob => {
                    // Create a link element to trigger download
                    const a = document.createElement('a');
                    const url = window.URL.createObjectURL(blob);
                    a.href = url;
                    // Set the file name dynamically from the URL (or hard-code it)
                    a.download = fileUrl.split('/').pop(); 
                    document.body.appendChild(a);
                    a.click();  // Trigger download
                    // Clean up
                    setTimeout(() => {
                        document.body.removeChild(a);
                        window.URL.revokeObjectURL(url);
                    }, 0);
                })
                .catch(error => console.error('Error downloading file:', error));
        });
    });
</script>
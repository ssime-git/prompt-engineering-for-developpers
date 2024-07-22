# Prompt Engineering for developpers

# Pour les boutons

```css
    include-after-body: 
      text: |
        <script>
        var customArrows = `
          <div class="custom-arrow left" onclick="Reveal.prev()"></div>
          <div class="custom-arrow right" onclick="Reveal.next()"></div>
        `;
        Reveal.addEventListener('ready', event => {
          document.body.insertAdjacentHTML('beforeend', customArrows);
        });
        </script>
```

et

```css
/* Custom Chevron Arrow Styles */
.custom-arrow {
    position: fixed;
    bottom: 20px;
    width: 40px;  /* Adjust width as needed */
    height: 40px; /* Adjust height as needed */
    background-color: #4a4a4a;
    cursor: pointer;
    transition: background-color 0.3s ease;
    z-index: 1000;
}

/* Chevron pointing left */
.custom-arrow.left {
    left: 10px;
    clip-path: polygon(0% 50%, 100% 0%, 100% 100%); /* Chevron pointing left */
}

/* Chevron pointing right */
.custom-arrow.right {
    right: 10px;
    clip-path: polygon(0% 0%, 100% 50%, 0% 100%); /* Chevron pointing right */
}

/* Hover State for Arrows */
.custom-arrow:hover {
    background-color: #666666; /* Slightly lighter grey on hover */
}

.logo {
    width: 200px; /* Adjust the width as needed */
    height: 200px; /* Maintain aspect ratio */
}

```
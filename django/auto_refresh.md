# auto\_refresh

```markup
<script>
  function show_progress_bar(percent) {
    const bar = document.querySelector("#bar");
    bar.hidden = false;

    const text = card.querySelector("#bar-text");
    text.textContent = `${percent}%`;
  }

  function hide_progress_bar() {
    const bar = document.querySelector("#bar");
    bar.hidden = true;
  }

  function refresh() {
    fetch(url)
      .then(response => response.json())
      .then(data => {
        show_progress_bar(data.percent);

        // call this function again later
        setTimeout(refresh, 5000);
      })
      .catch(error => {
        console.error(error);
        hide_progress_bar();
      });
  }

  refresh();
</script>
```

 


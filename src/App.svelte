<script>
  function fetchGet(url, data) {

    // let param = Object.keys(data)
    //     .map(k => encodeURIComponent(k) + '=' + encodeURIComponent(data[k]))
    //     .join('&');

    return fetch(url)
            .then(response => response.json())
  }

  let data = fetchGet("http://127.0.0.1:8099/chat/list");

  let question_list = Array();
  data.then(
    (data) => {
      question_list = data
      // console.log(data)
    }
  )
</script>
<ul>
  {#each question_list as question}
    <li>{question.subject}</li>
  {/each}
</ul>

<script>
  import Button from "@smui/button";
  import Card from "@smui/card";

  let colors = [
    "青",
    "茶色",
    "黄色",
    "緑",
    "水色",
    "薄紫",
    "黄緑",
    "黒",
    "白",
    "灰色",
    "肌色",
    "オレンジ",
  ];

  let result = localStorage.getItem("resultColor")
    ? localStorage.getItem("resultColor")
    : "まだ未定";

  const uranau = () => {
    let random = Math.random() * colors.length;
    result = colors[Math.floor(random)];
    localStorage.setItem("resultColor", result);
  };

  let resetText = "まだ未定にする";
</script>

<div class="content">
  <h1>
    あなたのラッキーカラーは{result}です
  </h1>
  <div style="display: flex;">
    <Button on:click={() => uranau()}>
      <h2>占う</h2>
    </Button>
    <Button
      on:click={() => {
        localStorage.removeItem("resultColor");
        resetText = "リロードが必要です";
      }}
    >
      <h2>{resetText}</h2>
    </Button>
  </div>
  <Card padded>
    色リスト
    {#each colors as color}
      <div>{color}</div>
    {/each}
  </Card>
</div>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Kosugi Maru", sans-serif;
  }

  :global(html, body) {
    margin: 0;
    padding: 0;
    font-size: 16px;
    background-color: #fafafa;
  }

  .content {
    display: contents;
  }
</style>

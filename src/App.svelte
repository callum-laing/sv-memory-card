<script>
  import Content from './lib/Content.svelte';
</script>



<h1>Memory Card</h1>
<main>
  <div>

    <Content />
  </div>

</main>

<footer>
  <h2>Copyright© 2024 Callum Laing</h2>
</footer>


<style>


  footer {
position: fixed;
    bottom: 0;
    width: 100%;
    text-align: center;
      font-family: "Kode Mono", monospace;
      font-size: .75rem;
  }

main {
  display: flex;
  align-items: center;
  justify-content: center;

}
div {
  width: 1250px;
  height: 500px;
  border: 2px solid black;
  border-radius: 10px;
    background: linear-gradient(to right top, #147878, #60db8e);
}

/* Mobile */
@media (max-width: 768px) {
    div {
      width: 100%;
      background-color: transparent;
      border: none;
      font-size: .8rem;
    }
}
</style>
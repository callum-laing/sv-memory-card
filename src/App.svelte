<script>
  import Content from './lib/Content.svelte';
</script>



<h1>Memory Card</h1>
<main>
  <div>

    <Content />
  </div>

</main>


<style>
main {
  display: flex;
  align-items: center;
  justify-content: center;

}
div {
  width: 1250px;
  height: 600px;
  border: 2px solid black;
  border-radius: 10px;
  background-color: rgba(20, 120, 120);
}
</style>
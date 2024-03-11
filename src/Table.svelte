<script lang="ts">
  import DataTable, {Head, Body, Row, Cell} from '@smui/data-table';
  import LinearProgress from '@smui/linear-progress';
  import Button from '@smui/button';
  export let items: any[] = [];
  export let loaded = false
</script>

<DataTable table$aria-label="lista de comidas" style="width: 100%">
  <Head>
    <Row>
      <Cell numeric>ID</Cell>
      <Cell>Nome</Cell>
      <Cell>Marca</Cell>
      <Cell numeric>Preço</Cell>
      <Cell numeric>Peso</Cell>
      <Cell numeric>Volume</Cell> 
    </Row>
  </Head>
  <Body>
    {#each items as item (item.id)}
      <Row>
        <Cell numeric>{item.id}</Cell>
        <Cell>{item.name}</Cell>
        <Cell>{item.brand}</Cell>
        <Cell>{item.cost}</Cell>
        <Cell>{item.weight}</Cell>
        <Cell>{item.volume}</Cell>
      </Row>
    {/each}
  </Body>

  
</DataTable>

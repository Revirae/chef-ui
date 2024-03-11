<script lang="ts">
  import { onMount } from 'svelte';
  import Table from "../components/Table.svelte"

  type Food = {
    id: {
      tb: string;
      id: {
        String: string;
      };
    };
    name: string;
    brand: string;
    cost: number;
    weight: number;
    volume: number;
  };

  let items: Food[] = [];
  let loaded = false;

  onMount(() => loadFood(false))

  function loadFood() {
    if(typeof fetch !== 'undefined') {
      loaded = false;

      fetch('http://localhost:8082/allfood')
        .then((response) => response.json())
        .then((json) =>
          setTimeout(
            () => {
              items = json;
              loaded = true;
            }, 50
          )
        );
    }
  }
</script>

<Table items={items} loaded={loaded} />
